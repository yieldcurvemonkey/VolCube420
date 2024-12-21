# VolCube420
- SOFR OIS (BBG ICVS 490 curve) Swaption Volatility Cube Data
- Data sourced from mix of different brokers and proprietary markings from the DTCC SDR
- NY EOD marks
- All in Normal Vol - thats current practice, divide by sqrt(252) for bpvol/daily vol
- ATMF Stike Offsets (bps): `[-200, -100, -50, -25, -10, 0, 10, 25, 50, 100, 200]`
- SABR Model calibrated using [Differential Evolution](https://en.wikipedia.org/wiki/Differential_evolution) with a Residual Sum of Squares objective function
- [Bilinear interpolation](https://en.wikipedia.org/wiki/Bilinear_interpolation) is used
- Schema for EOD JSON file:

```
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "Swaption Volatility Cube",
  "description": "A schema for validating swaption volatility cube data where keys represent strike offsets from the at-the-money forward (ATMF).",
  "type": "object",
  "patternProperties": {
    "^-\\d+$": {
      "description": "Strike offsets from the at-the-money forward (ATMF) in basis points. Keys are negative for strikes below ATMF.",
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "Option Tenor": {
            "type": "string",
            "description": "The tenor of the option (e.g., '1M', '3M', '6M', '1Y', etc.)."
          },
          "1Y": {
            "type": "number",
            "description": "Normal Volatility value for a swap with a 1-year maturity."
          },
          "2Y": {
            "type": "number",
            "description": "Normal Volatility value for a swap with a 2-year maturity."
          },
          "3Y": {
            "type": "number",
            "description": "Normal Volatility value for a swap with a 3-year maturity."
          },
          "4Y": {
            "type": "number",
            "description": "Normal Volatility value for a swap with a 4-year maturity."
          },
          "5Y": {
            "type": "number",
            "description": "Normal Volatility value for a swap with a 5-year maturity."
          },
          "6Y": {
            "type": "number",
            "description": "Normal Volatility value for a swap with a 6-year maturity."
          },
          "7Y": {
            "type": "number",
            "description": "Normal Volatility value for a swap with a 7-year maturity."
          },
          "8Y": {
            "type": "number",
            "description": "Normal Volatility value for a swap with an 8-year maturity."
          },
          "9Y": {
            "type": "number",
            "description": "Normal Volatility value for a swap with a 9-year maturity."
          },
          "10Y": {
            "type": "number",
            "description": "Normal Volatility value for a swap with a 10-year maturity."
          },
          "15Y": {
            "type": "number",
            "description": "Normal Volatility value for a swap with a 15-year maturity."
          },
          "20Y": {
            "type": "number",
            "description": "Normal Volatility value for a swap with a 20-year maturity."
          },
          "25Y": {
            "type": "number",
            "description": "Normal Volatility value for a swap with a 25-year maturity."
          },
          "30Y": {
            "type": "number",
            "description": "Normal Volatility value for a swap with a 30-year maturity."
          }
        },
        "required": ["Option Tenor"],
        "additionalProperties": false
      }
    }
  },
  "additionalProperties": false
}

```

