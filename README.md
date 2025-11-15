# Fuel Prices PT - TRMNL Plugin

A [TRMNL](https://usetrmnl.com/) plugin that displays real-time fuel prices (Gasolina 95) for gas stations in Vila Franca de Xira, Portugal. The data is fetched from the official Portuguese government fuel price database (DGEG - Direção-Geral de Energia e Geologia).

## Features

- 📊 Displays top 10 cheapest gas stations in the area
- 💰 Shows potential savings between cheapest and most expensive options
- 🔄 Polls for updates every 6 hours (360 minutes)
- 🎨 Multiple layout options: full, half (horizontal/vertical), and quadrant views
- 📍 Filters by district (Lisboa) and municipality (Vila Franca de Xira)

## Data Source

This plugin fetches data from the official Portuguese fuel price API:
- **API**: `precoscombustiveis.dgeg.gov.pt`
- **Fuel Type**: Gasolina simples 95 (unleaded gasoline 95)
- **Location**: Vila Franca de Xira, Distrito de Lisboa

## Project Structure

```
.
├── README.md
├── bin/
│   └── trmnlp                  # Convenience script to run trmnlp
├── certificates/
├── response_example.json       # Sample API response for testing
└── src/
    ├── full.liquid            # Full screen layout
    ├── half_horizontal.liquid # Half screen horizontal layout
    ├── half_vertical.liquid   # Half screen vertical layout
    ├── quadrant.liquid        # Quarter screen layout
    ├── settings.yml           # Plugin configuration
    └── shared.liquid          # Shared components/styles
```

## Getting Started

### Prerequisites

Choose one of the following options:

**Option 1: Ruby (recommended for development)**
- Ruby 3.x
- Firefox (optional, for PNG rendering)
- ImageMagick (optional, for PNG rendering)

**Option 2: Docker**
- Docker installed and running

### Installation

#### Option 1: Using RubyGems

```bash
gem install trmnl_preview
```

#### Option 2: Using Docker

No installation needed - the Docker image will be pulled automatically.

## Development

### Running Locally

The `bin/trmnlp` script is provided as a convenience and will automatically use the local Ruby gem if available, or fall back to Docker.

#### Using the provided script:

```bash
./bin/trmnlp serve
```

#### Or directly with Ruby:

```bash
trmnlp serve
```

#### Or directly with Docker:

```bash
docker run \
  --publish 4567:4567 \
  --volume "$(pwd):/plugin" \
  trmnl/trmnlp serve
```

The development server will start on `http://localhost:4567` and automatically reload when you make changes to the Liquid templates.

### Modifying the Plugin

1. Edit the Liquid templates in the `src/` directory:
   - `full.liquid` - Full screen layout
   - `half_horizontal.liquid` - Half screen horizontal layout
   - `half_vertical.liquid` - Half screen vertical layout
   - `quadrant.liquid` - Quarter screen layout

2. Modify `src/settings.yml` to change:
   - Polling interval
   - API parameters (municipality, fuel type, etc.)
   - Display settings

3. The development server will automatically detect changes and reload the preview

## Deployment to TRMNL

### First Time Setup

```bash
# Authenticate with TRMNL
trmnlp login

# Push your plugin to TRMNL
trmnlp push
```

### Updating an Existing Plugin

If you created this plugin using the TRMNL web editor, you can clone it locally:

```bash
# Authenticate
trmnlp login

# Clone the plugin (replace [id] with your plugin ID)
trmnlp clone fuel_pricing_pt [id]

# Make changes, then push updates
cd fuel_pricing_pt
trmnlp push
```

### Authentication

The `trmnlp login` command saves your API key to `~/.config/trmnlp/config.yml`.

Alternatively, you can set the `TRMNL_API_KEY` environment variable (useful for CI/CD pipelines):

```bash
export TRMNL_API_KEY=your_api_key_here
```

## Configuration

### Polling Settings

The plugin is configured to poll the API every 6 hours (360 minutes). You can modify this in `src/settings.yml`:

```yaml
strategy: polling
refresh_interval: 360  # minutes
```

### API Parameters

The current configuration searches for:
- **Fuel Type**: Gasolina simples 95 (ID: 3201)
- **District**: Lisboa (ID: 11)
- **Municipality**: Vila Franca de Xira (ID: 165)
- **Results per page**: 50

To change the search parameters, modify the `polling_url` in `src/settings.yml`.

## Testing

Use the included `response_example.json` file to test layouts without making API calls during development.

## Display Information

The plugin shows:
- Station ranking (1-10)
- Station name
- Brand
- Location
- Price (in €/liter)
- Last update date
- Maximum savings comparison

## License

This plugin is open source and available for personal and commercial use.

## Resources

- [TRMNL Official Site](https://usetrmnl.com/)
- [TRMNL Plugin Documentation](https://help.usetrmnl.com/en/articles/10542599-importing-and-exporting-private-plugins)
- [trmnlp GitHub Repository](https://github.com/usetrmnl/trmnlp)
- [Liquid Template Language](https://shopify.github.io/liquid/)
- [DGEG Fuel Prices API](https://precoscombustiveis.dgeg.gov.pt/)

## Contributing

Contributions are welcome! Feel free to submit issues or pull requests.
