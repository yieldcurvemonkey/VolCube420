# VolCube420
- SOFR OIS (BBG ICVS 490 curve) Swaption Volatility Cube Data
- Data sourced from mix of different brokers and proprietary markings from the DTCC SDR
- NY EOD marks
- All in Normal Vol - thats current practice, divide by sqrt(252) for bpvol/daily vol
- ATMF Stike Offsets (bps): `[-200, -100, -50, -25, -10, 0, 10, 25, 50, 100, 200]`
- [Bilinear interpolation](https://en.wikipedia.org/wiki/Bilinear_interpolation) is used
