### <a name="wpf-spell-checking-in-text-enabled-controls-will-not-work-in-windows-10-for-languages-not-in-the-oss-input-language-list"></a>WPF kontroly pravopisu v textu povoleno ovládací prvky nebudou fungovat ve Windows 10 pro jazyky, které nejsou v seznamu jazyk operačního systému.

|   |   |
|---|---|
|Podrobnosti|Při spuštění ve Windows 10, nástroj pro kontrolu pravopisu nemusí fungovat pro ovládací prvky WPF textu povoleno, protože jsou k dispozici pouze pro jazyky, které jsou k dispozici v seznamu jazyků funkce platformy pro kontrolu pravopisu. Ve Windows 10 když jazyk se přidá do seznamu dostupných klávesnice, Windows automaticky stáhne a nainstaluje odpovídající funkce na vyžádání (zámořských) balíčku, které poskytuje funkce pro kontrolu pravopisu. Přidáním jazyk do seznamu jazyků bude podporovaný nástroj pro kontrolu pravopisu.|
|Návrh|Mějte na paměti, že jazyk nebo text, který má být kontrola pravopisu je nutné přidat jako jazyk pro kontrolu pravopisu pro práci ve Windows 10.|
|Rozsah|Edge|
|Version|4.6|
|Typ|Modul runtime|

