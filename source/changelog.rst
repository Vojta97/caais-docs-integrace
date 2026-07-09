.. _changelog:

.. role:: ticket

=============
Verze a změny
=============

*Stručně popsané syntaktické či sémantické změny a opravy API od počátku roku 2026 – verze 2.17.*



verze 2.28 (2026-07-07)
-----------------------

- Nevracej v SAML response atribut `NotBefore` elementu `SubjectConfirmationData`. :ticket:`closes 636`

verze 2.27 (2026-06-23)
-----------------------

- Vracej v SAML response v atributu `Recipient` elementu `SubjectConfirmationData` URL endpointu (`AssertionConsumerServiceURL`). :ticket:`closes 511`


verze 2.26 (2026-06-09)
-----------------------

*Beze změn API.*


verze 2.25 (2026-05-26)
-----------------------

- Vracej záznamy v deterministickém pořadí při volání :ref:`HistoryData <ws:historydata>`. :ticket:`closes 359`


verze 2.24.5 (2026-05-19)
-------------------------


verze 2.23 (2026-04-21)
-----------------------


verze 2.22 (2026-04-14)
-----------------------

*Beze změn API.*

verze 2.21 (2026-04-10)
-----------------------

- Rozšiř funkcionalitu SAML 2.0 protokolu:

  - Umožni :ref:`NameId <api_saml:nameid>` ve formátu e-mailu. :ticket:`closes #200`.
  - Umožni :ref:`aliasing atributů <api_saml:attrs_aliasing>`. :ticket:`closes #201`.

verze 2.20 (2026-03-17)
-----------------------

*Beze změn API.*

verze 2.19 (2026-03-03)
-----------------------

- Oprav API JIP/KAAS editačních webových služeb:

  - Vracej správné časové řezy v ``HistoryDataResponse``. :ticket:`closes #324`

verze 2.18 (2026-02-04)
-----------------------

- Přidej persistentní atribut UUID pro subjekt. Předávej jej protokoly OIDC a SAML 2.0. :ticket:`closes #198`
- Vynuť předávání atributů v SAML 2.0 response bez explicitního požadavku jen na základě konfigurace AIS. :ticket:`closes #276`
- Oprav API JIP/KAAS editačních webových služeb:
  
  - Vracej v ``CreateUserResponse`` vždy atribut ``object-id``. :ticket:`fixes #310`
  - Změň časová razítka v odpovědích kvůli kompatibilitě s JIP/KAAS na unix timestamp v sekundách (původně milisekundy). :ticket:`fixes #321`
  - Oprav xmlns v ``GetVersionResponse`` pro edit/3. :ticket:`fixes #322`
  - Oprav stav zrušeno v ``GetOrganizationResponse``. :ticket:`fixes #326`
  - Oprav zpracování explicitních namespace. :ticket:`fixes #319`
  - Změn výchozí typ certifikátů v CAAIS IdP na komerční (původně kvalifikovaný). :ticket:`fixes #329`

verze 2.17 (2026-01-20)
-----------------------

- Aktualizuj API JIP/KAAS editačních webových služeb:

  - Vracej v ``getUserResponse`` boolean element ``isLocalAdmin``.
