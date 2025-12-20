# Fuel Prices PT - TRMNL Plugin

A [TRMNL](https://usetrmnl.com/) plugin that displays real-time fuel prices for gas stations in Districts and Municipalities from Portugal. The data is fetched from the official Portuguese government fuel price database (DGEG - Direção-Geral de Energia e Geologia).

## Features

- 📊 Displays top 10 cheapest gas stations in the area
- 💰 Shows potential savings between cheapest and most expensive options
- 🔄 Polls for updates every 6 hours (360 minutes)
- 🎨 Multiple layout options: full, half (horizontal/vertical), and quadrant views
- 📍 Filters by district (required) and optionally by municipality
- 🎛️ Configurable fuel type selection (Gasoline 95/98, Diesel, GPL, etc.)
- ✨ Enhanced layouts with improved readability and data presentation

## Data Source

This plugin fetches data from the official Portuguese fuel price API:
- **API**: `precoscombustiveis.dgeg.gov.pt`

#### Fuel Type IDs

| Fuel Type | ID |
|-----------|---:|
| Gasolina simples 95 | 3201 |
| Gasolina simples 98 | 3400 |
| Gasóleo simples | 2101 |
| Gasolina especial 95 | 3205 |
| Gasolina especial 98 | 3405 |
| Gasoleo especial | 2105 |
| GPL Auto | 1120 |

Source: https://precoscombustiveis.dgeg.gov.pt/api/PrecoComb/GetTiposCombustiveis

#### District IDs

| District | ID |
|----------|---:|
| Aveiro | 1 |
| Beja | 2 |
| Braga | 3 |
| Bragança | 4 |
| Castelo Branco | 5 |
| Coimbra | 6 |
| Évora | 7 |
| Faro | 8 |
| Guarda | 9 |
| Leiria | 10 |
| Lisboa | 11 |
| Portalegre | 12 |
| Porto | 13 |
| Santarém | 14 |
| Setúbal | 15 |
| Viana do Castelo | 16 |
| Vila Real | 17 |
| Viseu | 18 |

Source: https://precoscombustiveis.dgeg.gov.pt/api/PrecoComb/GetDistritos

#### District and Municipality IDs

| District | Municipality | ID |
|----------|--------------|---:|
| **Aveiro** (1) | Águeda | 1 |
| | Albergaria-a-Velha | 2 |
| | Anadia | 3 |
| | Arouca | 4 |
| | Aveiro | 5 |
| | Castelo de Paiva | 6 |
| | Espinho | 7 |
| | Estarreja | 8 |
| | Mealhada | 10 |
| | Murtosa | 11 |
| | Oliveira de Azeméis | 12 |
| | Oliveira do Bairro | 13 |
| | Ovar | 14 |
| | Santa Maria da Feira | 15 |
| | Sever do Vouga | 17 |
| | São João da Madeira | 16 |
| | Vagos | 18 |
| | Vale de Cambra | 19 |
| | Ílhavo | 9 |
| **Beja** (2) | Aljustrel | 20 |
| | Almodôvar | 21 |
| | Alvito | 22 |
| | Barrancos | 23 |
| | Beja | 24 |
| | Castro Verde | 25 |
| | Cuba | 26 |
| | Ferreira do Alentejo | 27 |
| | Moura | 29 |
| | Mértola | 28 |
| | Odemira | 30 |
| | Ourique | 31 |
| | Serpa | 32 |
| | Vidigueira | 33 |
| **Braga** (3) | Amares | 34 |
| | Barcelos | 35 |
| | Braga | 36 |
| | Cabeceiras de Basto | 37 |
| | Celorico de Basto | 38 |
| | Esposende | 39 |
| | Fafe | 40 |
| | Guimares | 42 |
| | Guimarães | 41 |
| | Póvoa de Lanhoso | 43 |
| | Terras de Bouro | 44 |
| | Vieira do Minho | 45 |
| | Vila Nova de Famalicão | 46 |
| | Vila Verde | 48 |
| | Vizela | 49 |
| **Bragança** (4) | Alfândega da Fé | 50 |
| | Bragança | 51 |
| | Carrazeda de Ansiães | 52 |
| | Freixo de Espada à Cinta | 53 |
| | Macedo de Cavaleiros | 54 |
| | Miranda do Douro | 55 |
| | Mirandela | 56 |
| | Mogadouro | 57 |
| | Torre de Moncorvo | 58 |
| | Vila Flor | 59 |
| | Vimioso | 60 |
| | Vinhais | 61 |
| **Castelo Branco** (5) | Belmonte | 62 |
| | Castelo Branco | 63 |
| | Covilhã | 64 |
| | Fundão | 65 |
| | Idanha-a-Nova | 66 |
| | Oleiros | 67 |
| | Penamacor | 68 |
| | Proença-a-Nova | 69 |
| | Sertã | 70 |
| | Vila Velha de Ródão | 72 |
| | Vila de Rei | 71 |
| **Coimbra** (6) | Arganil | 73 |
| | Cantanhede | 74 |
| | Coimbra | 75 |
| | Condeixa-a-Nova | 76 |
| | Figueira da Foz | 77 |
| | Góis | 78 |
| | Lousã | 79 |
| | Mira | 80 |
| | Miranda do Corvo | 81 |
| | Montemor-o-Velho | 82 |
| | Oliveira do Hospital | 83 |
| | Pampilhosa da Serra | 84 |
| | Penacova | 85 |
| | Penela | 86 |
| | Soure | 87 |
| | Tábua | 88 |
| | Vila Nova de Poiares | 89 |
| **Évora** (7) | Alandroal | 90 |
| | Arraiolos | 91 |
| | Borba | 92 |
| | Estremoz | 93 |
| | Montemor-o-Novo | 95 |
| | Mora | 96 |
| | Mourão | 97 |
| | Portel | 98 |
| | Redondo | 99 |
| | Reguengos de Monsaraz | 100 |
| | Vendas Novas | 101 |
| | Viana do Alentejo | 102 |
| | Vila Viçosa | 103 |
| | Évora | 94 |
| **Faro** (8) | Albufeira | 104 |
| | Alcoutim | 105 |
| | Aljezur | 106 |
| | Castro Marim | 107 |
| | Faro | 108 |
| | Lagoa | 109 |
| | Lagos | 110 |
| | Loulé | 111 |
| | Monchique | 112 |
| | Olhão | 113 |
| | Portimão | 114 |
| | Silves | 116 |
| | São Brás de Alportel | 115 |
| | Tavira | 117 |
| | Vila Real de Santo António | 119 |
| | Vila do Bispo | 118 |
| **Guarda** (9) | Aguiar da Beira | 120 |
| | Almeida | 121 |
| | Celorico da Beira | 122 |
| | Figueira de Castelo Rodrigo | 123 |
| | Fornos de Algodres | 124 |
| | Gouveia | 125 |
| | Guarda | 126 |
| | Manteigas | 127 |
| | Meda | 128 |
| | Pinhel | 129 |
| | Sabugal | 130 |
| | Seia | 131 |
| | Trancoso | 132 |
| | Vila Nova de Foz Côa | 133 |
| **Leiria** (10) | Alcobaça | 134 |
| | Alvaiázere | 135 |
| | Ansião | 136 |
| | Batalha | 137 |
| | Bombarral | 138 |
| | Caldas da Rainha | 139 |
| | Castanheira de Pêra | 140 |
| | Figueiró dos Vinhos | 141 |
| | Leiria | 142 |
| | Marinha Grande | 143 |
| | Nazaré | 144 |
| | Pedrógão Grande | 146 |
| | Peniche | 147 |
| | Pombal | 148 |
| | Porto de Mós | 149 |
| | Óbidos | 145 |
| **Lisboa** (11) | Alenquer | 150 |
| | Amadora | 151 |
| | Arruda dos Vinhos | 152 |
| | Azambuja | 153 |
| | Cadaval | 154 |
| | Cascais | 155 |
| | Lisboa | 156 |
| | Loures | 157 |
| | Lourinhã | 158 |
| | Mafra | 159 |
| | Odivelas | 160 |
| | Oeiras | 161 |
| | Sintra | 162 |
| | Sobral de Monte Agraço | 163 |
| | Torres Vedras | 164 |
| | Vila Franca de Xira | 165 |
| **Portalegre** (12) | Alter do Chão | 166 |
| | Arronches | 167 |
| | Avis | 168 |
| | Campo Maior | 169 |
| | Castelo de Vide | 170 |
| | Crato | 171 |
| | Elvas | 172 |
| | Fronteira | 173 |
| | Gavião | 174 |
| | Marvão | 175 |
| | Monforte | 176 |
| | Nisa | 177 |
| | Ponte de Sor | 178 |
| | Portalegre | 179 |
| | Sousel | 180 |
| **Porto** (13) | Amarante | 181 |
| | Baião | 182 |
| | Felgueiras | 183 |
| | Gondomar | 184 |
| | Lousada | 185 |
| | Maia | 186 |
| | Marco de Canaveses | 187 |
| | Matosinhos | 188 |
| | Paredes | 190 |
| | Paços de Ferreira | 189 |
| | Penafiel | 191 |
| | Porto | 192 |
| | Póvoa de Varzim | 193 |
| | Santo Tirso | 194 |
| | Trofa | 195 |
| | Valongo | 196 |
| | Vila Nova de Gaia | 198 |
| | Vila do Conde | 197 |
| **Santarém** (14) | Abrantes | 199 |
| | Alcanena | 200 |
| | Almeirim | 201 |
| | Alpiarça | 202 |
| | Benavente | 203 |
| | Cartaxo | 204 |
| | Chamusca | 205 |
| | Constância | 206 |
| | Coruche | 207 |
| | Entroncamento | 208 |
| | Ferreira do Zêzere | 209 |
| | Golegã | 210 |
| | Mação | 211 |
| | Ourém | 212 |
| | Rio Maior | 213 |
| | Salvaterra de Magos | 214 |
| | Santarém | 215 |
| | Sardoal | 216 |
| | Tomar | 217 |
| | Torres Novas | 218 |
| | Vila Nova da Barquinha | 219 |
| **Setúbal** (15) | Alcochete | 221 |
| | Alcácer do Sal | 220 |
| | Almada | 222 |
| | Barreiro | 223 |
| | Grândola | 224 |
| | Moita | 225 |
| | Montijo | 226 |
| | Palmela | 227 |
| | Santiago do Cacém | 228 |
| | Seixal | 229 |
| | Sesimbra | 230 |
| | Setúbal | 231 |
| | Sines | 232 |
| **Viana do Castelo** (16) | Arcos de Valdevez | 233 |
| | Caminha | 234 |
| | Melgao | 236 |
| | Melgaço | 235 |
| | Monção | 237 |
| | Paredes de Coura | 238 |
| | Ponte da Barca | 239 |
| | Ponte de Lima | 240 |
| | Valença | 241 |
| | Viana do Castelo | 242 |
| | Vila Nova de Cerveira | 243 |
| **Vila Real** (17) | Alijó | 245 |
| | Boticas | 246 |
| | Chaves | 247 |
| | Mesão Frio | 248 |
| | Mondim de Basto | 249 |
| | Montalegre | 250 |
| | Murça | 251 |
| | Peso da Régua | 252 |
| | Ribeira de Pena | 253 |
| | Sabrosa | 254 |
| | Santa Marta de Penaguião | 255 |
| | Valpaços | 256 |
| | Vila Pouca de Aguiar | 257 |
| | Vila Real | 258 |
| **Viseu** (18) | Armamar | 259 |
| | Carregal do Sal | 260 |
| | Castro Daire | 261 |
| | Cinfães | 262 |
| | Lamego | 263 |
| | Mangualde | 264 |
| | Moimenta da Beira | 265 |
| | Mortágua | 266 |
| | Nelas | 267 |
| | Oliveira de Frades | 268 |
| | Penalva do Castelo | 269 |
| | Penedono | 270 |
| | Resende | 271 |
| | Santa Comba Dão | 272 |
| | Sernancelhe | 276 |
| | Sátão | 275 |
| | São João da Pesqueira | 273 |
| | São Pedro do Sul | 274 |
| | Tabuaço | 277 |
| | Tarouca | 278 |
| | Tondela | 279 |
| | Vila Nova de Paiva | 280 |
| | Viseu | 281 |
| | Vouzela | 282 |

Source: https://precoscombustiveis.dgeg.gov.pt/api/PrecoComb/GetMunicipios

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

The plugin can be configured through the TRMNL web interface with the following options:

- **Fuel Type**: Select from dropdown (default: Gasolina simples 95, ID: 3201)
  - Gasolina Simples 95, 98
  - Gasóleo Simples/Especial
  - GPL Auto
  - And more
- **District**: Select from dropdown (default: Lisboa, ID: 11)
  - All 18 Portuguese districts available
- **Municipality**: Optional text field (leave empty to search entire district)
  - Example: 165 for Vila Franca de Xira
  - See tables above for complete list of municipality IDs
- **Results per page**: 20 stations (fixed)

These settings can be configured directly in the TRMNL web interface without editing code.

## Testing

Use the included `response_example.json` file to test layouts without making API calls during development.

## Display Information

The plugin shows:
- Station ranking (up to 10 stations depending on layout)
- Station name and brand
- Location (municipality/locality)
- Price (in €/liter)
- Last update date
- Maximum savings comparison (difference between cheapest and highest price)

**Layout Capacities:**
- Full layout: Displays up to 10 stations
- Half layouts (horizontal/vertical): Displays up to 10 stations
- Quadrant layout: Displays up to 5 stations

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
