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
    address public communityReserve = 0xd2845388C1788f0CAEDF9c6028cdF9c0EfeF538b  // Neue community

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
Das Konzept der "Mahoki Green Lung Revolution" zielt darauf ab, ökologische Nachhaltigkeit durch die Einführung eines eigenen ERC20-Tokens zu fördern. Dieser Token dient als Anreizmechanismus, um umweltfreundliche Projekte zu unterstützen und die Community aktiv einzubinden.

**Token-Details:**

- **Name:** Mahoki Green Lung Revolution
- **Symbol:** MGLR
- **Initiale Gesamtmenge:** 500 Millionen MGLR
- **Maximale Gesamtmenge:** 1 Milliarde MGLR

**Verteilung der initialen Token:**

- **30%** (150 Millionen MGLR) für den ICO
- **25%** (125 Millionen MGLR) für Partnerschaften und Ökosystem-Entwicklung
- **20%** (100 Millionen MGLR) für Umweltprojekte
- **15%** (75 Millionen MGLR) für das Entwicklerteam
- **10%** (50 Millionen MGLR) für Community-Incentives

**Smart Contract Funktionen:**

- **Minting:** Der Vertrag ermöglicht es dem Eigentümer, neue Tokens zu erstellen, solange die maximale Gesamtmenge nicht überschritten wird.
- **Aktualisierung der Reserve-Adressen:** Der Eigentümer kann die Adressen für die verschiedenen Reserves bei Bedarf ändern.

**Implementierung des Smart Contracts:**

Der Smart Contract wurde in Solidity geschrieben und nutzt die OpenZeppelin-Bibliotheken für ERC20 und Ownable. Dies gewährleistet Sicherheit und Standardkonformität. Die spezifischen Adressen für die Reserves wurden entsprechend den Anforderungen festgelegt.

**Nächste Schritte:**

1. **Überprüfung und Testen des Smart Contracts:** Stellen Sie sicher, dass der Vertrag gründlich getestet wurde, um Fehler zu vermeiden.
2. **Deployment auf der Blockchain:** Veröffentlichen Sie den Smart Contract auf der gewünschten Blockchain-Plattform.
3. **Verifizierung des Contracts:** Nach dem Deployment sollte der Vertrag auf Plattformen wie Etherscan verifiziert werden, um Transparenz zu gewährleisten.
4. **Bekanntmachung des Projekts:** Nutzen Sie soziale Medien, Foren und andere Kanäle, um die Community über das Projekt zu informieren und zur Teilnahme zu motivieren.

Dieses Konzept bietet eine solide Grundlage, um ökologische Initiativen durch den Einsatz von Kryptowährungen zu unterstützen und eine engagierte Community aufzubauen. 
