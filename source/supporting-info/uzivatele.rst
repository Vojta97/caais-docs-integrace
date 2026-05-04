.. _si:users:

======================
Uživatelské účty CAAIS
======================

Při zakládání nového uživatelského účtu v CAAIS se předvyplní uživatelské jméno ve tvaru **jmeno_prijmeni**, popřípadě doplněné ještě prefixem subjektu a číselným suffixem, aby bylo globálně unikátní. Výchozí hodnotu uživatelského jména lze upravit dle zvyklostí úřadu nebo přání uživatele, jen musí být globálně unikátní – nesmí být zabrané jiným uživatelem. V průběhu 2026H2 připravujeme funkcionalitu změny uživatelského jména u již existujícího účtu.

Pokud AIS potřebuje persistentní identitu uživatele, nesmí k tomuto používat uživatelské jméno (*username*), nýbrž pseudonym (OIDC *sub*, SAML *PersonIdentifier*) ve formátu UUID, u něhož CAAIS zaručuje jeho trvalost a neměnnost.

V průběhu 2026H2 chystáme funkcionalitu získání AIFO přihlašovaného uživatele pomocí služeb :abbr:`ISZR (Informační systém základních registrů)` E175 – isrtUlozMapaAifo a E176 – iszrPodejMapaAifo.


Vztah k uživatelským účtům v JIP/KAAS
-------------------------------------

Neexistuje žádný apriorní vztah mezi uživatelským jménem v JIP/KAAS a uživatelským jménem CAAIS. Je pouhá koincidence (byť častá), přísluší-li stejné uživatelské jméno v JIP/KAAS a v CAAIS i stejnému reálnému uživateli.

Pokud AIS obsahuje data vázaná k identitě uživatele, je možné zvolit jednu ze dvou strategií dle povahy dat:

Pro *trvale vázaná data* je výhodné identity sloučit, což obnáší úpravu AIS. Uživatel se do AIS (poprvé) přihlásí pomocí CAAIS a systém ho vyzve, aby se přihlásil ještě jednou pomocí JIP/KAAS. Po současném úspěšném přihlášení v obou autentizačních systémech se obě uživatelovy identity na straně AIS trvale sloučí a uživatel bude mít přístup ke stejným datům, ať se přihlašuje prostřednictvím JIP/KAAS nebo CAAIS.

Pro *přechodně vázaná data* (například v rámci workflow) lze ponechat identity oddělené. Rozpracovaná workflow uživatel dokončí pod svou identitou v JIP/KAAS, nová workflow začíná pod svou identitou v CAAIS. Přechodné období tak jest lze řešit metodickým opatřením bez nutnosti upravovat AIS.


Identity v auditních záznamech
------------------------------

Vede-li si AIS audit o činnosti přihlášeného uživatele, postačuje, pokud eviduje, prostřednictvím kterého autentizačního systému a pod jakou identitou se uživatel přihlásil. Pro tento účel není nutné identity mezi JIP/KAAS a CAAIS vázat.
