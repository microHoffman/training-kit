---
layout: cheat-sheet
redirect_to: false
title: GitHub Git Cheat Sheet
byline: Git is the open source distributed version control system that facilitates GitHub activities on your laptop or desktop. This cheat sheet summarizes commonly used Git command line instructions for quick reference.
leadingpath: ../../
---

{% capture colOne %}
## Instalace

### GitHub pro Windows a Mac
[desktop.github.com](https://desktop.github.com)

### Git pro všechny platformy
[git-scm.com](https://git-scm.com)

## Konfigurace
Nastavení informací o uživateli pro všechny lokální repozitáře

```$ git config --global user.name "[jmeno]"```

Nastaví jméno, které bude přiřazené ke commitům

```$ git config --global user.email "[email]"```

Nastaví email, který bude přiřazený ke commitům

```$ git config --global color.ui auto```

Aktivuje barevné zvýrazňování výstupů z přikazového řádku

## Branches

Větve (branches) jsou důležitou součástí práce s Gitem. Jakýkoliv commit který vytvoříte bude vytvořen na aktuální větvi ve které se nacházíte. Použijte `git status` pro zjištění v jaké větvi se momentálně nacházíte.

```$ git branch [jmeno-vetve]```

Vytvoří novou větev

```$ git switch -c [jmeno-vetve]```

Přepne se do specifikované větve a aktualizuje pracovní adresář

```$ git merge [jmeno-vetve]```

Sloučí změny v dané větvi do větve ve které se aktuálně nacházíte. Tato operace se nejčastěji dělá přes pull requests, ale jedná se o důležitou Git operaci.

```$ git branch -d [jmeno-vetve]```

Smaže specifikovanou větev

{% endcapture %}
<div class="col-md-6">
{{ colOne | markdownify }}
</div>


{% capture colTwo %}

## Vytváření repozitářů

Nový repozitář může být vytvořen lokálně nebo existující repozitář může být naklonován. Pokud byl repozitář vytvořen lokálně, je nutné poté pushnout změny do GitHubu.

```$ git init```

Vytvoří nový git repozitář ve složce ve které se aktuálně nacházíte. Po zavolání `git init` přikazu prolinkujte lokální repozitář s prázdným GitHub repozitářem pomocí následujícího příkazu:

```$ git remote add origin [url]```

Specifikuje vzdálený repozitář pro váš lokální repozitář. Url míří na GitHub repozitář.

```$ git clone [url]```

Naklonuje (stáhne) již existující repozitář na GitHubu včetně všech souborů, větví a commitů.

## Soubor .gitignore

Občas je nutné některé soubory vylouřit z trackování Gitem. Toto je nejčastěji provedeno ve speciálním souboru s názvem `.gitignore`. Na stránce [github.com/github/gitignore](https://github.com/github/gitignore) můžete najít užitečné ukázky `.gitignore` souborů.

## Synchronizace z,ěm Synchronize changes

Synchronizace vašeho lokálního repozitáře se vzdáleným repozitářem na GitHub.com.

```$ git fetch```

Stáhne všechny změny z větví na vzdáleném repozitáři

```$ git merge```

Sloučí vzdálenou větev do lokální větve

```$ git push```

Nahraje všechny změny v lokální větvi na GitHub

```$ git pull```

Aktualizuje vaši lokální větev o nové commity z příslušné vzdálené větve na GitHubu. `git pull` je kombinací příkazů `git fetch` a `git merge`.

{% endcapture %}
<div class="col-md-6">
{{ colTwo | markdownify }}
</div>
<div class="clearfix"></div>

{% capture colThree %}

## Dělná změn

Prohlížení a kontrola vývoje souborů

```$ git log```

Vypíše historii verzí (commitů) pro konkrétní větev

```$ git log --follow [file]```

Vypíše verzovací historii pro konkrétní soubor kromě přejmenování. Funguje pouze s jedním souborem.

```$ git diff [first-branch]...[second-branch]```

Vypíše odlišnosti mezi dvěma větvemi

```$ git show [commit]```

Vypíše metadata a změny ve specifikovaném commitu

```$ git add [file]```

Přidá soubor do "balíčku" pro nový commit

```$ git commit -m "[descriptive message]"```

Vytvoří commit se specifikovanou zprávou (většinou shrnutí změn, které byly provedeny)

## Vrácení změn

Napravení chyb a nahrazení historie

```$ git reset [commit]```

Vrátí zpátky všechny provedené změny až po daný commit, zachovává lokální změny

```$ git reset --hard [commit]```

Zahodí všechnu historii a změny až po daný commit

> POZOR! Se změnou historie můžou přijít vážné nežádoucí vedlejší efekty. Pokud potřebujete změnit commity které již existují na GitHubu (vzdáleném repozitáři), postupujte prosím opatrně. Pokud potřebujete pomoci, neváhejte se obrátit na [github.community](https://github.community) nebo kontaktujte podporu.

{% endcapture %}
<div class="col-md-6">
{{ colThree | markdownify }}
</div>

{% capture colFour %}

## Glosář

- **git**: distribuovaný open source verzovací systém
- **GitHub**: platforma pro hostování a kolaboraci s Git repozitáři
- **commit**: Git objekt, záznam (snapshot) celého repozitáře komprimovaného do SHA
- **branch**: lehký pohyblivý ukazatel na commit
- **clone**: lokální verze repozitáře včetně všech commitů a větví
- **remote**: společný repozitář na GitHubu, kteří mohou využívat všichni členové týmu pro synchronizaci změn
- **fork**: kopie repozitáře na GitHubu vlastněného jiným uživatelem
- **pull request**: místo pro porovnání a diskuzi nad změnami do určité větve, je možné komentovat a schvalovat změny, provádět integrované testy a mnohé další
- **HEAD**: reprezentuje současný pracovní adresát. HEAD ukzatel může být posunut na jiné větve, tagy nebo commity použitím `git switch`

{% endcapture %}
<div class="col-md-6">
{{ colFour | markdownify }}
</div>
<div class="clearfix"></div>
