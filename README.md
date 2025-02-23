# CipherCore-FHE 🔒🔑

**Librairie open-source pour expérimenter la cryptographie homomorphe (Fully Homomorphic Encryption)**  
*Protégez vos calculs sensibles sans déchiffrer les données*

## Fonctionnalités Clés
- 🛡️ Support des schémas FHE (BFV, CKKS, BGV)
- 📦 Intégration transparente avec SEAL, OpenFHE et HElib
- 🚀 Exemples prêts à l'emploi : votes chiffrés, scoring de crédit
- 🔌 Plugins pour Python, Node.js et WebAssembly
- 📊 Benchmarks automatisés avec Grafana

## Structure du Projet

```bash

CipherCore-FHE/
├── src/
│ ├── core/ # Code C++ principal
│ └── bindings/ # Liaisons pour autres langages
├── examples/
│ ├── medical/ # Cas d'usage santé
│ └── finance/ # Applications financières
├── docs/
│ ├── API.md # Documentation technique
│ └── threat_model.pdf # Analyse de sécurité
├── tests/
│ ├── unit/ # Tests unitaires
│ └── fuzz/ # Tests de robustesse
├── dependencies/
│ ├── SEAL/ # Sous-module Microsoft SEAL
│ └── OpenFHE/ # Sous-module OpenFHE
├── Dockerfile # Configuration pour conteneurs
├── CMakeLists.txt # Build system
├── Makefile # Commandes utilitaires
├── .gitignore
└── LICENSE # Licence Apache 2.0

```

## Démarrage Rapide (Ubuntu)
```bash
git clone --recursive https://github.com/valorisa/CipherCore-FHE

cd CipherCore-FHE

make deps # Installe SEAL et OpenFHE

make build # Compile le projet

make test # Exécute les tests
```

## Exemple : Addition Homomorphe
```cpp
#include "ciphercore.hpp"

int main() {
auto ctx = CipherCore::Context(CipherCore::Scheme::CKKS);
ctx.genKeys();


double x = 3.5, y = 7.1;
auto encX = ctx.encrypt(x);
auto encY = ctx.encrypt(y);

auto encResult = encX + encY;
std::cout << "Résultat déchiffré : " << ctx.decrypt(encResult) << std::endl;
}
```

## Contribution
1. 🍴 Fork du dépôt
2. 🌿 Créez une branche : `git checkout -b feature/ma-nouvelle-fonction`
3. 💡 Committez vos changements
4. 🚀 Push vers la branche
5. 🔄 Soumettez une Pull Request

*Licence : Apache 2.0 | Maintenu par valorisa*
