# Poznámky pro seminární práce pro předmět KI/KDIB

Témata:

6. Zálohovací technologie pro koncové prvky
7. Zálohovací technologie pro infrastrukturní systémy
8. Archivační technologie

# Zálohovací technologie pro koncové prvky (Endpoint data backup)

0. Proč zálohovat koncové prvky?
1. Jakou technologii je vhodné nasadit pro zálohování osobních dat koncového uživatele?
2. Co je RPO a RTO?
3. Jaké aspekty má zálohování osobních dat?
4. Jaké vlastnosti dat je nezbytné analyzovat před volbou zálohovacích či archivačních technologií?

## 0. Proč zálohovat koncové prvky?
- V dnešní době jedním z nejčastějších kyberůtoků je Ransomware, který zašifruje buď specifická data (složky, soubory) nebo celý prvek (laptop, vzdáleně přístupný workstation).
- Selhání úložného média.

## 1. Jakou technologii je vhodné nasadit pro zálohování osobních dat koncového uživatele?
 - Cloudové uložiště - veřejný cloud, privátní cloud, oboje 
 - Využití přechodného uložiště, které může sbírat data od všech koncových uživatelů a ve kterém je zpracováno, než přejde do finálního uložiště. Může šifrovat data.
 - Komerční: 
    - AWS
    - google drive
    - OneDrive
    - Microsoft Azure
 - Nekomerční:
    - OwnCloud
    - Ceph
 - Uživatelská data jsou synchronizovaná s cloudem. 


## 2. Co je RPO a RTO?
RTO - Recovery Time Objective:
- Specifikovaná ideální doba mezi ztrátou přístupu k datům a obnovení dat do funkčního stavu.

RPO - Recovery Point Objective:
- Specifikovaná ideální doba mezi poslední zálohou a ztrátou přístupu k datům, neboli jak velké množství ztracených dat neovlivní organizaci.
    Maximum tolerable data loss for the specific organization
    Industry-specific factors — businesses dealing with sensitive information such as financial transactions or health records must update more often
    Data storage options, such as physical files versus cloud storage, can affect the speed of recovery
    The cost of data loss and lost operations
    Compliance schemes include provisions for disaster recovery, data loss, and data availability that may affect businesses
    The cost of implementing disaster recovery solutions

Platí pro oboje:
- Ideálně specifikováno seniorními manažery v organizaci podle zkušeností s obnovou dat.

## 3. Jaké aspekty má zálohování osobních dat?
- Originální data zůstávají přístupná, zatímco záloha je v jiné lokaci
- Jsou ponechány pouze užitečné zálohy, zatímco staré a neužitečné zálohy jsou odstraněny.
- Zálohy musí být na rychle dostupném místě, pro co nejefektivnější obnovení dat.



## 4. Jaké vlastnosti dat je nezbytné analyzovat před volbou zálohovacích či archivačních technologií?
- Hodnota dat: Jak moc jsou do budoucna potřebná? Jestli stačí krátkodobé zálohy, nebo je nutné déle archivovat. 
- Dostupnost a obnova dat: Jak rychle musí být data dostupná a jak rychle je lze obnovit v případě potřeby. To je důležité zejména pro kritická data, která by měla být okamžitě dostupná.
- Retenční politiky: Zvážit dobu, po kterou musí být data uchovávána. Některá data mohou vyžadovat dlouhodobé uchování kvůli právním předpisům nebo regulacím.
- Objem dat: Objem dat může mít vliv na výběr technologií pro zálohování a archivaci. Může být nutné využít škálovatelné řešení pro zvládání velkých objemů dat.
- Typy dat: Například strukturovaná data, nestrukturovaná data, soubory, databáze, obrázky nebo videa. Různé typy dat mohou vyžadovat různé technologie pro zálohování nebo archivaci.
- Bezpečnost dat: Zvážit bezpečnostní požadavky na data. To zahrnuje zabezpečení dat v případě zálohování nebo archivace, ochranu před neoprávněným přístupem a možnost šifrování dat.
- Doba potřebná pro zálohování nebo archivaci: Jak rychle musí být data zálohována nebo archivována. Zohlednit dobu, která je k dispozici pro provádění těchto operací a jejich vliv na běžící systémy.
- Náklady: Posoudit náklady spojené s různými zálohovacími nebo archivačními technologiemi. Zvážit náklady na pořízení a provoz těchto technologií a také případné dodatečné náklady na správu a údržbu.

# Zálohovací technologie pro infrastrukturní systémy

1. Jakou technologii zvolit pro zálohování serverových sdílených uložišť?
2. Jakou technologii použít pro řešení odolnosti virtualizačních platforem?
3. Co je distribuované uložiště?
4. Jaké technologie a protokoly využijeme v rámci distribuovaných uložišť?
5. Co je deduplikace dat?
6. Co je replikace dat?

## 1. Jakou technologii zvolit pro zálohování serverových sdílených uložišť?
- Zálohování na místě (On-Premises): Tato metoda zahrnuje vytvoření záloh přímo na místě vašeho datacentra nebo serverové místnosti. Můžete použít specializovaný zálohovací software nebo hardwarová zařízení. Tato možnost vám poskytuje přímou kontrolu nad zálohovacím procesem a daty.

- Cloudové zálohování: Využití cloudových služeb pro zálohování je stále populárnější. Můžete vybrat z různých poskytovatelů cloudových zálohovacích služeb, kteří vám umožní zálohovat vaše serverová sdílená uložiště do jejich cloudové infrastruktury. Tím se snižuje potřeba vlastnit a spravovat vlastní hardwarové zařízení pro zálohování.

- Zrcadlení dat (Replication): Tato metoda zahrnuje vytvoření repliky serverových sdílených uložišť na jiném místě nebo na jiných serverech. Tím se zajišťuje redundantnost dat a obnova v případě výpadku nebo katastrofy. Replikace dat může být prováděna buď na místě (on-premises) nebo do cloudu.

- Zálohování na pásku (Tape Backup): Páskové zálohování je tradiční metoda zálohování, která využívá pásky pro ukládání dat. Pásková média poskytují vysokou kapacitu a dlouhodobou archivaci. Tato metoda je obzvláště užitečná pro velká datová množství, která nevyžadují častou obnovu.

- RAID (Redundant Array of Independent Disks): Technologie pro ukládání dat, která využívá skupinu pevných disků k vytvoření jednoho logického úložiště s vyšší výkonností, odolností a/nebo kapacitou.

- Hybridní řešení: Můžete také zvážit kombinaci různých technologií zálohování. Například kombinaci zálohování na místě a v cloudu, kdy se část dat zálohuje na místě a část je replikována do cloudového prostředí.


- NAS (Network Attached Storage): Technologie pro ukládání dat, která umožňuje sdílení datového úložiště v rámci lokální sítě. NAS je samostatné zařízení, které slouží jako specializovaný server pro ukládání dat a poskytuje síťový přístup k těmto datům.
- SAN (Storage Area Network): Technologie pro ukládání dat, která umožňuje vytvoření vyhrazeného a vysokorychlostního sítěového prostoru pro přístup k úložištím dat. SAN je navržen tak, aby poskytoval rychlý a spolehlivý přístup ke sdíleným úložištím dat pro servery a další zařízení v síti.

## 2. Jakou technologii použít pro řešení odolnosti virtualizačních platforem?
- High Availability (HA): High Availability je technologie, která zajišťuje neustálou dostupnost virtuálních strojů (VM) a aplikací v případě výpadku fyzického serveru. Systém pro vysokou dostupnost monitoruje stav serverů a v případě výpadku automaticky migruje běžící VM na jiný dostupný server.

- Clusterování: Vytvoření clusteru virtuálních serverů umožňuje sdílení zdrojů a zajišťuje vysokou dostupnost. Pokud jeden server selže, ostatní servery v clusteru převezmou práci a zajistí neustálou dostupnost VM a aplikací.

- Duplicity dat: Duplicitní uložení dat zajišťuje jejich ochranu v případě selhání. To může zahrnovat replikaci dat mezi serverovými farmami nebo zrcadlení diskových polí pro rychlou obnovu v případě poruchy.

- Zálohování a obnova dat: Pravidelné zálohování virtuálních strojů a dat je nezbytné pro obnovu v případě katastrofy. Zálohování by mělo být prováděno pravidelně a zálohovací kopie by měly být uloženy na odlišném úložišti nebo v cloudu.

- Monitorování a správa: Systémy pro monitorování a správu virtualizačních platforem jsou důležité pro rychlé zjištění a řešení problémů. Monitorování v reálném čase umožňuje identifikovat výpadky, výkonnostní problémy a umožňuje přijmout opatření před většími problémy.

## 3. Co je distribuované uložiště?
- Distribuované uložiště je koncept, který se vztahuje k architektuře nebo systému, ve kterém jsou data uložena na více zařízeních, která mohou být fyzicky umístěna na různých místech a propojena pomocí sítě. Tato zařízení spolupracují a vytvářejí jedno logické úložiště, které je uživatelům přístupné a zobrazuje se jako jediná entita.
- Spolehlivost proti výpadkům.
- Snadná škálovatelnost.
- Výkonnost díky paralelnímu zpracování dat na více zařízeních.
- Geografická redundance: Replikace dat na více geografických místech.

## 4. Jaké technologie a protokoly využijeme v rámci distribuovaných uložišť?
- Distribuované souborové systémy: Technologie jako GFS (Google File System), GlusterFS, Ceph a Hadoop HDFS (Hadoop Distributed File System) umožňují distribuci souborů a jejich replikaci na více zařízeních v síti. Tyto systémy poskytují abstrakci nad fyzickými úložišti a zajišťují jejich koordinaci, sdílení a přístup k datům.

- Protokoly pro sdílení souborů: Protokoly jako NFS (Network File System) a SMB/CIFS (Server Message Block/Common Internet File System) slouží k sdílení souborů mezi různými zařízeními v distribuovaném uložišti. Tyto protokoly umožňují přístup a práci se soubory prostřednictvím síťového spojení.

- Replikační protokoly: Replikační protokoly, jako je RSync a BitTorrent Sync, se používají pro replikaci dat mezi různými zařízeními v distribuovaném uložišti. Tyto protokoly umožňují synchronizaci dat mezi uzly a zajišťují, aby byla data dostupná a aktuální na všech zařízeních.

- Clusterování a sdílení zdrojů: Pro sdílení zdrojů a koordinaci mezi zařízeními v distribuovaném uložišti se využívají technologie jako clusterování (např. Pacemaker, Heartbeat) a sdílené sítěové souborové systémy (např. GFS2, Lustre). Tyto technologie zajišťují správu a synchronizaci zdrojů mezi zařízeními.

- Protokoly pro komunikaci: V rámci distribuovaných uložišť se využívají různé protokoly pro komunikaci mezi zařízeními, jako jsou TCP/IP, UDP (User Datagram Protocol) a RPC (Remote Procedure Call). Tyto protokoly umožňují přenos dat, řízení spojení a koordinaci operací mezi jednotlivými uzly distribuovaného uložiště.

## 5. Co je deduplikace dat?
Deduplikace dat je technika, která se používá k identifikaci a eliminaci redundantních kopií dat v rámci úložiště. Při deduplikaci jsou identifikovány stejné nebo podobné bloky dat a je uchována pouze jedna instance každého bloku, zatímco všechny ostatní odkazují na tuto instanci. Tím se minimalizuje potřeba uložit a zálohovat redundantní kopie dat, což vede ke snížení spotřeby úložného prostoru a optimalizaci správy dat.

Deduplikace dat může být prováděna na různých úrovních:

- Bloková deduplikace: Data jsou rozdělena do menších bloků (typicky několik kilobytů nebo menších) a každý blok je analyzován na unikátnost. Pokud se identifikuje blok, který již existuje v úložišti, není potřeba ukládat redundantní kopii, ale pouze se odkazuje na existující instanci.

- Souborová deduplikace: Místo deduplikace na úrovni bloků se data rozdělují na soubory a porovnávají se mezi sebou. Pokud se identifikuje soubor se stejným obsahem, stačí uložit pouze jeden exemplář souboru.

- Deduplikace na úrovni virtuálních strojů (VM): V případě virtualizace se deduplikace provádí na úrovni VM, což umožňuje identifikaci a odstranění redundantních kopií virtuálních disků a dalších komponent VM.

Deduplikace dat přináší několik výhod:

- Úspora úložného prostoru: Deduplikace snižuje požadovanou kapacitu úložiště tím, že eliminuje redundantní kopie dat. To může být zvláště užitečné při zálohování, archivaci a dlouhodobém uchovávání dat.

- Snížení nákladů na úložiště: S menší potřebou fyzického úložiště se snižují náklady na pořízení, provoz a správu úložištní infrastruktury.

- Rychlejší zálohování a obnova dat: S deduplikací se snižuje objem dat, která je třeba zálohovat a obnovovat, což vede ke zrychlení těchto procesů.

## 6. Co je replikace dat?
Replikace dat je proces vytváření a udržování identických kopií dat na různých zařízeních nebo umístěních. Cílem replikace je zajistit dostupnost a odolnost dat v případě výpadku, selhání nebo katastrofy jednoho zdrojového umístění.

Při replikaci jsou data duplikována a uchovávána na více místech, přičemž každá replika obsahuje stejný obsah. Změny v datech jsou propagovány na všechny repliky, aby se zajistila jejich konzistence. Pokud dojde k výpadku nebo ztrátě dat na jednom umístění, mohou být data stále dostupná z jiné repliky.

Replikace dat může být prováděna na různých úrovních:

- Bloková replikace: Data jsou rozdělena do menších bloků a tyto bloky jsou replikovány na různá umístění. Tím se minimalizuje ztráta dat v případě výpadku nebo chyby na jednom umístění.

- Souborová replikace: Místo replikace na úrovni bloků se celé soubory duplikují na různá umístění. Tím se zajistí, že v případě problémů s jedním umístěním jsou soubory dostupné z jiného umístění.

- Replikace na úrovni datového centra: Data jsou replikována mezi různými datovými centry, což zajišťuje geografickou redundanci a zvýšenou odolnost v případě výpadku celého datového centra nebo regionu.

Replikace dat přináší několik výhod:

- Vysoká dostupnost: Díky replikaci jsou data dostupná i v případě selhání nebo výpadku jednoho umístění. Uživatelé mohou nadále přistupovat a pracovat s daty z jiných replik.

- Odolnost vůči chybám: Pokud dojde k chybě nebo ztrátě dat na jednom umístění, replikované kopie poskytují záložní zdroj dat a minimalizují riziko ztráty dat.

- Rychlá obnova dat: V případě ztráty dat na jednom umístění lze rychle obnovit data z replikovaných kopií, čímž se minimalizuje doba nedostupnosti a obnova.

# Archivační technologie

1. Co je archivace dat?
2. Jak mají být data archivována v závislosti na jejich citlivost?
3. Jak se liší archivace osobních a firemních dat?
4. Co jsou komprimační algoritmy a kdy se využívají?
5. Jakou technologii je vhodné využít pro zajištění více četných archivů a proč?

## 1. Co je archivace dat?
- Archivace dat se odlišuje od běžného ukládání a správy dat. Jedná se o proces uchovávání dat dlouhodobě, obvykle pro účely budoucí reference, historického uchování, právních nebo regulačních požadavků a dalších důvodů. Archivace dat zajišťuje, že data zůstanou dostupná, chráněná a integrovaná po celou dobu svého životního cyklu.

Archivace dat obvykle zahrnuje následující prvky:

- Identifikace dat: Identifikují se a vybírají se důležitá data, která mají být archivována. Tato data mohou zahrnovat dokumenty, záznamy, soubory, elektronickou poštu, databáze a další.

- Klasifikace a řízení: Data jsou klasifikována na základě jejich významu, hodnoty, zachování a právních požadavků. Stanovují se pravidla a politiky pro řízení a uchovávání archivovaných dat.

- Zabezpečení: Archivovaná data musí být chráněna před ztrátou, poškozením nebo neoprávněným přístupem. To zahrnuje opatření jako zálohování, šifrování, kontrola integrity dat a zajištění přístupových práv.

- Dlouhodobé uchovávání: Archivovaná data jsou uchovávána po dlouhou dobu, která může být měřena v letech nebo desetiletích. Je důležité zvolit vhodné médium pro uchovávání dat, které je odolné vůči degradaci a zajišťuje jejich dlouhodobou dostupnost.

- Indexace a vyhledávání: Pro usnadnění vyhledávání a přístupu k archivovaným datům se používají indexační mechanismy a metadatové informace. To umožňuje rychlé a efektivní vyhledávání požadovaných dat.

- Kontrola integrity a migrace: Pravidelně se provádí kontrola integrity archivovaných dat a provádí se migrace na nová média nebo formáty, aby byla zajištěna dlouhodobá čitelnost a dostupnost dat.

## 2. Jak mají být data archivována v závislosti na jejich citlivost?
Způsob, jakým jsou data archivována, závisí na jejich citlivosti a požadavcích na ochranu soukromí a bezpečnost. Zde jsou některé přístupy k archivaci dat v závislosti na jejich citlivosti:

- Veřejně dostupná data: Pokud se jedná o veřejně dostupná data, která neobsahují žádné citlivé informace, mohou být archivována v otevřených formátech, jako jsou veřejné webové archivy, open data platformy nebo veřejné knihovny. Přístup k nim by měl být snadný a bez omezení.

- Citlivá korporátní data: Pro citlivá korporátní data, jako jsou firemní dokumenty, finanční záznamy nebo obchodní tajemství, je obvykle vyžadováno vyšší zabezpečení. Tato data by měla být archivována v systému s přísným řízením přístupu, šifrováním a mechanismy pro sledování a auditování přístupu.

- Osobní a citlivá data: Pokud jde o osobní data, jako jsou zdravotní záznamy, identifikační údaje nebo finanční informace, platí přísná pravidla ochrany soukromí. Tato data by měla být archivována s důrazem na dodržování předpisů ochrany osobních údajů, jako je například GDPR (Obecné nařízení o ochraně osobních údajů). To zahrnuje šifrování dat, anonymizaci, omezený přístup a možnost odstranění dat na požádání.

- Regulovaná data: Pro data, která podléhají přísným regulačním požadavkům, jako jsou účetní záznamy, lékařské záznamy nebo právní dokumenty, je zapotřebí splnit specifické normy archivace. To může zahrnovat dlouhodobé uchovávání, auditovatelnost, verzování a záznamy o změnách.

## 3. Co jsou komprimační algoritmy a kdy se využívají?
Komprimační algoritmy jsou algoritmy používané ke snižování velikosti datových souborů nebo datových proudů. Cílem je redukovat množství potřebného úložného prostoru nebo snížit přenosovou rychlost dat. Komprese dat se využívá v mnoha oblastech, včetně komprese souborů, komunikace dat, archivace a zálohování.

Existují dva základní typy komprese:

- Ztrátová komprese (Lossy): Ztrátová komprese je technika, při které dochází k trvalé ztrátě části informace při kompresi dat. Tento typ komprese se často používá pro média, jako jsou zvukové nebo obrazové soubory, kde drobné ztráty nejsou významné. Příklady ztrátových kompresních algoritmů zahrnují JPEG pro obrazová data nebo MP3 pro zvuková data.

Bezztrátová komprese (Lossless): Bezztrátová komprese je technika, která umožňuje obnovení původních dat bez jakékoliv ztráty informace. Tento typ komprese je vhodný pro soubory, které vyžadují přesnou reprodukci původních dat, jako jsou textové soubory nebo programové kódy. Bezztrátové kompresní algoritmy se snaží identifikovat opakující se vzorce nebo redundantní informace v datech a nahradit je kratšími reprezentacemi. Příklady bezztrátových kompresních algoritmů zahrnují ZIP pro soubory, PNG pro obrazová data nebo FLAC pro zvuková data.

Využití komprese dat je rozsáhlé a zahrnuje následující případy:

- Úspora úložného prostoru: Komprese dat umožňuje ušetřit místo na úložišti, což je užitečné zejména při archivaci a zálohování dat.

- Rychlejší přenos dat: Komprese dat snižuje velikost datových souborů, což vede ke snížení času potřebného pro jejich přenos přes síť.

- Optimalizace paměti: V některých případech je komprese dat užitečná pro optimalizaci paměťových nároků, například při ukládání dat v operační paměti nebo při komunikaci mezi zařízeními s omezenou pamětí.

- Zvýšení výkonu: Komprese dat může také přinést výhody výkonu, protože snížení velikosti datových souborů nebo datových proudů může zkrátit čas potřebný pro jejich zpracování.

## 4. Jakou technologii je vhodné využít pro zajištění více četných archivů a proč?

Erasure coding je metoda pro redundanci dat, která umožňuje rozdělit data na menší kousky, zakódovat je a distribuovat mezi různá úložiště nebo servery.

Existuje několik důvodů, proč je erasure coding vhodnou technologií pro více četné archivy:

- Odolnost proti výpadkům: Erasure coding umožňuje rozdělit data na několik fragmentů a zakódovat je tak, že lze obnovit původní data z pouze části fragmentů. To znamená, že i když selže některé úložiště nebo server, data lze stále obnovit. Erasure coding poskytuje vyšší odolnost proti výpadkům než tradiční metody, jako je zrcadlení dat (RAID 1), které vyžadují redundantní kopie všech dat.

- Úspora úložného prostoru: Erasure coding umožňuje dosáhnout větší úspory úložného prostoru ve srovnání s tradičními metodami redundantního ukládání dat. Namísto ukládání plných kopií dat lze použít pouze část fragmentů k obnovení původních dat. To znamená, že lze dosáhnout vyššího poměru mezi velikostí původních dat a spotřebovaným úložným prostorem.

- Efektivní využití šířky pásma: Erasure coding umožňuje rozdělit data na fragmenty, které lze distribuovat mezi různé servery nebo úložiště. To umožňuje paralelní přenos dat mezi těmito zařízeními, což vede ke zvýšení využití šířky pásma a rychlejšímu přenosu dat.

- Škálovatelnost: Erasure coding je dobře škálovatelnou technologií, která umožňuje snadné přidávání dalších úložišť nebo serverů do systému. Lze jednoduše rozšiřovat kapacitu a výkon systému bez nutnosti duplikace všech dat.



# Zdroje
S úpravou textu pomáhal ChatGPT.

Zálohování pro koncové prvky a infrastrukturní systémy:
- https://www.parablu.com/wp-content/uploads/2017/02/SMB-Guide-for-Cloud-Endpoint-Backup-Parablu_old_may2017.pdf
- http://www.measurecontrol.com/wp-content/uploads/2017/05/gartner-seguridad-en-la-nube.pdf
- https://www.msp360.com/resources/blog/backup-vs-archive/
- https://virtualizationreview.com/Articles/2015/06/01/High-Availability.aspx
- https://cloudian.com/guides/data-backup/distributed-storage/
- https://www.nutanix.com/info/distributed-storage
- https://en.wikipedia.org/wiki/Distributed_data_store
- https://www.netapp.com/data-management/what-is-data-deduplication/
- https://redis.com/blog/what-is-data-replication/

Archivace dat:
- https://www.druva.com/glossary/what-is-data-archiving-definition-and-related-faqs
- https://www.dataprotection.ie/en/individuals/data-protection-basics/principles-data-protection
- https://en.wikipedia.org/wiki/Data_compression
- https://dzone.com/articles/crunch-time-10-best-compression-algorithms
- https://blog.fileformat.com/2021/09/03/lossy-and-lossless-compression-algorithms/
- https://blog.min.io/erasure-coding/
- https://stonefly.com/blog/understanding-erasure-coding




