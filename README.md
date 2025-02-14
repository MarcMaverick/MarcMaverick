// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract MahokiGreenLungRevolution is ERC20, Ownable {
    uint256 public constant INITIAL_SUPPLY = 500_000_000 * 10**18; // 500 Millionen MGLR
    uint256 public constant MAX_SUPPLY = 1_000_000_000 * 10**18;  // 1 Milliarde MGLR

    // Adressen für verschiedene Zwecke
    address public projectReserve = 0x9c6C6a3b902241911DB26c7d5a84A5872E6844A6; // Projektadresse
    address public partnershipReserve = 0x3c4ED40D6a0987B93Ae64d99ad62fA9A746E86C4; // Partnerschaftsadresse
    address public teamReserve = 0xc34E9AcDa81374c0f9597b96a99C6ee1078714F2; // Neue Teamadresse
    address public communityReserve = 0x7890abcdef1234567890abcdef1234567890abcd;

    constructor() ERC20("Mahoki Green Lung Revolution", "MGLR") {
        // Initiale Zuteilung
        _mint(msg.sender, INITIAL_SUPPLY * 30 / 100); // 30% für ICO
        _mint(partnershipReserve, INITIAL_SUPPLY * 25 / 100); // 25% für Partnerschaften und Ökosystem-Entwicklung
        _mint(projectReserve, INITIAL_SUPPLY * 20 / 100); // 20% für Umweltprojekte
        _mint(teamReserve, INITIAL_SUPPLY * 15 / 100); // 15% für das Entwicklerteam
        _mint(communityReserve, INITIAL_SUPPLY * 10 / 100); // 10% für Community-Incentives
    }

    // Mint-Funktion, um neue Tokens zu erstellen (nur durch den Besitzer)
    function mint(address to, uint256 amount) external onlyOwner {
        require(totalSupply() + amount <= MAX_SUPPLY, "Max supply exceeded");
        _mint(to, amount);
    }

    // Funktion, um die Adressen für verschiedene Reserves zu ändern
    function updateReserves(
        address _projectReserve,
        address _partnershipReserve,
        address _teamReserve,
        address _communityReserve
    ) external onlyOwner {
        projectReserve = _projectReserve;
        partnershipReserve = _partnershipReserve;
        teamReserve = _teamReserve;
        communityReserve = _communityReserve;
    }
}
