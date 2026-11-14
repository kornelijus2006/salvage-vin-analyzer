# Salvage VIN Analyzer

Paste the VIN of a Copart or IAAI car, add a few photos, and see what it really costs to buy, import, repair and resell in Lithuania, and how that compares with retail prices on Autoplius and Mobile.de.

Built solo for the Unfair Weekend hackathon (graded remote track), starting 9 November 2026.

**Live demo:** https://claude.ai/artifact/XBig6ujNDKYWGDSMyypZzG

## The problem

People who buy damaged cars at US auctions (Copart, IAAI) and import them to Europe often misjudge the real cost. The bid is only part of it. Auction fees, shipping, customs duty, VAT, local registration and, above all, repairs can turn an apparent bargain into a loss. Buyers also can't easily tell how much cheaper a repaired car is than the same car on the local market.

## What it does

1. **VIN check.** Validates the format and the check digit, and catches typos.
2. **VIN decoding.** Claude estimates the make, model, year, engine, trim, likely equipment packages and whether it is a special edition.
3. **Photo reading.** The user pastes up to 4 auction photos. Claude describes the visible damage and reads the odometer. Without photos, it assumes typical damage.
4. **Landed cost.** The user enters only the car price, without fees. The app adds auction fees, US transport, ocean freight, insurance, port fees, customs duty, VAT and local costs. All rates are editable.
5. **Repair estimate.** A line-by-line table with original (OEM) parts, non-original parts and labor, plus the full cost to get the car road-ready each way. Each part has links to search for it.
6. **Market comparison.** Retail price ranges for Autoplius and Mobile.de, a comparison with similar cars (base version, this version, special edition), a suggested asking price and what a buyer saves.
7. **Maximum bid.** For cars still on auction, it shows the highest price to bid and still reach a target profit.

A simpler manual version is included in `salvage-flip-calculator.html`. It does the same cost math without AI.

## Important: what is real and what is estimated

- The fee, shipping, duty and VAT math is calculated by the app from editable defaults. The defaults are rough, so use your forwarder's real numbers.
- The VIN decode, damage description, repair prices and retail prices are **AI estimates**, not live listings, a mechanic's quote or an official VIN report.
- Equipment and edition information can be wrong. Confirm it with the seller or the build sheet.
- Mileage can't be read from a VIN. It comes from the odometer in the photos or from the user.

## Limitations

- Copart and IAAI do not allow automatic photo or price lookups, so the user adds photos by hand.
- The AI analysis only works when the page is opened in Claude. Opened elsewhere, the VIN check and fee calculation work but the AI analysis does not.
- No backend or database, and no live market data.

## What's next

- A server connected to a licensed auction and parts-data source, so photos, damage, mileage and sold prices load automatically from the VIN.
- Live Autoplius and Mobile.de market data.
- Direct links to specific parts shops and exact part numbers matched to the VIN.
- Saved cars, comparisons between several cars and shareable reports.

## Files

- `salvage-vin-analyzer-v2.html`: the main app.
- `salvage-flip-calculator.html`: the manual cost calculator.

Each is a single self-contained HTML file with no build step.

## Disclosure

All code in this repository was written during the hackathon window, starting 9 November 2026, with no earlier code reused. I don't write code myself, so I built it with Claude (Anthropic) as my AI coding assistant, directing the idea, the product decisions and the testing. The app's analysis feature also uses Claude at runtime.

## Author

Kornelijus Bagdžius, ISM University of Management and Economics.
