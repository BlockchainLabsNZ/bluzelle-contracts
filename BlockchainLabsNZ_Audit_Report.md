# Bluzelle Audit Report

## Preamble
This audit report was undertaken by BlockchainLabs.nz for the purpose of providing feedback to Bluzelle. It has subsequently been shared publicly without any express or implied warranty.

Solidity contracts were sourced from the public Github repo [njmurarka/ico-solidity](https://github.com/njmurarka/ico-solidity) prior to commit [542b5ca38d7cfc2292e1bb135b8ee10679e54d23](https://github.com/njmurarka/ico-solidity/tree/542b5ca38d7cfc2292e1bb135b8ee10679e54d23) - we would encourage all community members and token holders to make their own assessment of the contracts.

## Scope
All Solidity code contained in [/contracts](https://github.com/BlockchainLabsNZ/bluzelle-contracts/tree/542b5ca38d7cfc2292e1bb135b8ee10679e54d23) was considered in scope along with the tests contained in [/tests](https://github.com/BlockchainLabsNZ/bluzelle-contracts/tree/542b5ca38d7cfc2292e1bb135b8ee10679e54d23/tests) as a basis for static and dynamic analysis.

## Focus Areas
The audit report is focused on the following key areas - though this is not an exhaustive list.
### Correctness
- No correctness defects uncovered during static analysis?
- No implemented contract violations uncovered during execution?
- No other generic incorrect behaviour detected during execution?
- Adherence to adopted standards such as ERC20?
### Testability
- Test coverage across all functions and events?
- Test cases for both expected behaviour and failure modes?
- Settings for easy testing of a range of parameters?
- No reliance on nested callback functions or console logs?
- Avoidance of test scenarios calling other test scenarios?
### Security
- No presence of known security weaknesses?
- No funds at risk of malicious attempts to withdraw/transfer?
- No funds at risk of control fraud?
- Prevention of Integer Overflow or Underflow?
### Best Practice
- Explicit labeling for the visibility of functions and state variables?
- Proper management of gas limits and nested execution?
- Latest version of the Solidity compiler?

## Focus Areas
The audit report is focused on the following key areas - though this is not an exhaustive list.
### Correctness
- No correctness defects uncovered during static analysis?
- No implemented contract violations uncovered during execution?
- No other generic incorrect behaviour detected during execution?
- Adherence to adopted standards such as ERC20?
### Testability
- Test coverage across all functions and events?
- Test cases for both expected behaviour and failure modes?
- Settings for easy testing of a range of parameters?
- No reliance on nested callback functions or console logs?
- Avoidance of test scenarios calling other test scenarios?
### Security
- No presence of known security weaknesses?
- No funds at risk of malicious attempts to withdraw/transfer?
- No funds at risk of control fraud?
- Prevention of Integer Overflow or Underflow?
### Best Practice
- Explicit labeling for the visibility of functions and state variables?
- Proper management of gas limits and nested execution?
- Latest version of the Solidity compiler?

## Classification
### Defect Severity
- Minor - A defect that does not have a material impact on the contract execution and is likely to be subjective.
- Moderate - A defect that could impact the desired outcome of the contract execution in a specific scenario.
- Major - A defect that impacts the desired outcome of the contract execution or introduces a weakness that may be exploited.
- Critical - A defect that presents a significant security vulnerability or failure of the contract across a range of scenarios.

## Findings
### Minor
- **Remove updateWhitelist.txt** - `Best practice` Looks like it was added by mistake, there is already a `.js` version in the same directory  [View on GitHub](https://github.com/BlockchainLabsNZ/bluzelle-contracts/issues/5)
  - [ ] Not Fixed
- **Avoid magic numbers for bonus percentage** - `Best practice` We recommend avoiding the use of magic numbers, using a variable here would improve readability and make the code more maintainable for the futre.     [View on GitHub](https://github.com/BlockchainLabsNZ/bluzelle-contracts/issues/3)
  - [ ] Not Fixed
- **Add a README.md file outlining deployment steps to increase transparency** -  We recommend adding a README.md file detailing deployment steps so contributors can best understand the procedure of participating [View on GitHub](https://github.com/BlockchainLabsNZ/polymath-contracts/blob/master/README.md)
  - [ ] Not Fixed
- **There is no safety check for setting the bonus to 0** - `Question` In the prior version of the contract there was a safety check so that you couldn't [set the bonus to 0](https://github.com/njmurarka/ico-solidity/commit/19f69dd76c5a0aa19658dd0dd689387e15261d42#diff-5dee561713991ff0349ab72bdb179aa6L175) This has been removed, is this intentional or a mistake?   [View on GitHub](https://github.com/BlockchainLabsNZ/bluzelle-contracts/issues/4)
  - [ ] Not Fixed

### Moderate
- None found

### Major
- None found

### Critical
- None found

## Testing

To further satisfy test coverage, both `BluzelleToken.sol` and `BluzelleTokenSale.sol` were deployed onto the Kovan Test Network to achieve simulation of a mock sale. This can be viewed in the [Kovan_Tests.md](https://github.com/BlockchainLabsNZ/bluzelle-contracts/blob/master/Kovan_Tests.md) checklist.

## Conclusion

Overall we have been fully satisfied with the resulting contracts following the audit feedback period. We took part in carefully reviewing all source code provided, including deployment testing.

We are pleased to report that no potential vulnerabilities were uncovered during the audit. That the token complies with the recently finalised ERC20 Token Standards. The code has excellent testability and the developers have followed common best practices.

Of the issues we have raised all of them are minor. This crowdsale has a low risk of ethereum being hacked or stolen. 
