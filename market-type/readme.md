# What is this?
This directory contains a interpretable random forest classifier that attempts to classify the next quarter as either a sellers or buyers market. 
The model will operate on a quarterly timeframe.

# Output
The model has a single binary output;
- 1 for a sellers market
- 0 for a buyers market

A 'Sellers' market is a time where the demand on houses outweighs supply and drives up house prices. A 'Buyers' market is where supply outweighs demand and house prices either stagnate or decline.

The target label for any instance of data will be determined by the following;
- 1 (seller's market): the 3-month average months of supply is < 4.0.
- 0 (buyer's market): the 3-month average months of supply is > 5.5.
- If the months of supply falls between 4.0 and 5.5, consult the auction clearance rate. If it is > 65%, label as sellers's market (1); otherwise, label as buyers's market (0).

Note that after these target labels are calculated, the labels will need to be shifted by one in order to predict one quarter in the future.

# Input
The model takes data from the ABS. The measurements taken from the ABS are;
- the OCR (official cash rate)
- real mortgage rate (nominal - inflation)
- cpi index (inflation)

<em>below are demand features</em>
- investor share (percent of new loan commitment's value coming from investors)
- fhb share (percent of owner occupier new loan commitments that are from first home buyers)
- lending momentum (quarterly percentage change in the total value of new loan commitments)

<em>below are supply features
- building approvals (total dwelling units total)

<strong>features not yet with data nor engineered</strong>
- building approvals per capita
- unemployment rate
- rental vacancy rates
- Westpac-Melbourne Institute Index 'time to buy dwelling' index