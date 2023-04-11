# Providers

**Last Updated:** 2023-03-27

The table below lays out the providers with the associated provider `id` that can be used in the `payroll_provider` parameter for [Finch Connect](../Integrating-with-Finch/Integrate-Finch-Connect/Overview.md).

<!--
type: tab
title: HRIS
-->

<!-- theme: info -->
> **Read Census + Pay Data:** The `Company`, `Directory`, `Individual`, `Employment`, `Payment` and `Pay Statement` endpoint are read-only endpoints. Providers can be either an [Automated API Provider](../Product-Guides/Automated-Connect-Flow.md) or an [Assisted API Provider](../Product-Guides/Assisted-Connect-Flow.md).

<!-- theme: info -->
> **Write Benefits:** The benefits endpoints contain both read and write functionalities. Providers can be either an Automated API Benefit Provider or an Assisted API Benefit Provider. Only `Create Benefit`, `Update Benefit`, `Enroll Individuals in Benefits` and `Unenroll Individuals from Benefits` endpoints are available for Assisted API Benefit Providers.

### Automated API Providers
Display Name | Id | Read Census + Pay Data | Write Benefits
---------|----------|----------|----------
ADP Workforce Now† | `adp_workforce_now` | <span style="color:darkgreen">Automated</span> | <span style="color:goldenrod">Assisted**</span>
BambooHR | `bamboo_hr` | <span style="color:darkgreen">Automated</span> | <span style="color:goldenrod">Assisted**</span>
bob | `bob` | <span style="color:darkgreen">Automated</span> | <span >Not Supported</span>
Gusto | `gusto` | <span style="color:darkgreen">Automated</span> | <span style="color:darkgreen">Automated</span>
Humaans | `humaans` | <span style="color:darkgreen">Automated</span> | <span>Not Supported</span>
Insperity | `insperity` | <span style="color:darkgreen">Automated</span> | <span style="color:goldenrod">Assisted</span>
Justworks | `justworks` | <span style="color:darkgreen">Automated</span> | <span style="color:goldenrod">Assisted**</span>
Namely | `namely` | <span style="color:darkgreen">Automated</span> | <span style="color:goldenrod">Assisted</span>
Paychex Flex | `paychex_flex` | <span style="color:darkgreen">Automated</span> | <span style="color:goldenrod">Assisted**</span>
Paycom | `paycom` | <span style="color:darkgreen">Automated</span> | <span style="color:goldenrod">Assisted</span>
Paylocity | `paylocity` | <span style="color:darkgreen">Automated</span> | <span style="color:goldenrod">Assisted</span>
Personio | `personio` | <span style="color:darkgreen">Automated</span> | <span>Not Supported</span>
QuickBooks Payroll | `quickbooks` | <span style="color:darkgreen">Automated</span> | <span style="color:goldenrod">Assisted**</span>
Rippling | `rippling` | <span style="color:darkgreen">Automated</span> | <span >Not Supported</span>
Run Powered by ADP | `adp_run` | <span style="color:darkgreen">Automated</span> | <span style="color:goldenrod">Assisted**</span>
Sage HR | `sage_hr` | <span style="color:darkgreen">Automated</span> | <span style="color:goldenrod">Assisted</span>
Sapling | `sapling` | <span style="color:darkgreen">Automated</span> | <span>Not Supported</span>
Sequoia One | `sequoia_one` | <span style="color:darkgreen">Automated</span> | <span style="color:goldenrod">Assisted</span>
Square Payroll | `square_payroll` | <span style="color:darkgreen">Automated</span> | <span style="color:goldenrod">Assisted</span>
TriNet | `trinet` | <span style="color:darkgreen">Automated</span> | <span style="color:goldenrod">Assisted**</span>
UltiPro (UKG Pro) | `ulti_pro` | <span style="color:darkgreen">Automated</span> | <span style="color:goldenrod">Assisted</span>
Wave | `wave` | <span style="color:darkgreen">Automated</span> | <span style="color:goldenrod">Assisted**</span>
Workday | `workday` | <span style="color:darkgreen">Automated</span> | <span style="color:goldenrod">Assisted</span>
Zenefits | `zenefits` | <span style="color:darkgreen">Automated</span> | <span style="color:goldenrod">Assisted**</span>

### Assisted API Providers
Display Name | Id | Read Census + Pay Data | Write Benefits
---------|----------|----------|----------
AAP iSolved | `aap_isolved` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Abacus HCM iSolved | `abacus_isolved` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Absolute Payroll iSolved | `absolute_isolved` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Accupay iSolved | `accupay_isolved` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Ace Workforce Technologies isolved | `ace_isolved` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
AccountantsWorld | `accountantsworld` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Adams Keegan | `adams_keegan` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
ADP Comprehensive Services | `adp_comprehensive` | <span style="color:goldenrod">Assisted*</span> | <span style="color:goldenrod">Assisted</span>
ADP TotalSource | `adp_totalsource` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Advantage Payroll Services | `advantage_payroll_services` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Affiliated HR Payroll Services iSolved | `affiliated_hr_payroll_services_isolved` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Affiliated HR Payroll Services Evolution | `affiliated_hr_payroll_services_evolution` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Ahola | `ahola` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
AlphaStaff | `alphastaff` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Amplify HR | `amplify_hr` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Apdata | `apdata` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
APS Payroll | `aps_payroll` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Asset HR | `asset_hr` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Asure Software | `asure_software` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Balance Point | `balance_point` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Baron Payroll iSolved | `baron_isolved` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
BASIC | `basic` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
BBCS Payroll | `bbcs` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
BBSI | `bbsi` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
BCN Services | `bcn_services` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Bene-Care | `benecare` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Big Fish Employer Services | `big_fish_employer_services` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Bizchecks Payroll | `bizchecks_payroll` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Business Online Payroll | `business_online_payroll` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Ceridian Dayforce | `ceridian_dayforce` | <span style="color:goldenrod">Assisted*</span> | <span style="color:goldenrod">Assisted</span>
Ceridian Powerpay | `ceridian_powerpay` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Cezanne HR | `cezannehr` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
CharlieHR | `charlie_hr` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
ClickUp | `clickup` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
CoAdvantage | `coadvantage` | <span style="color:goldenrod">Assisted*</span> | <span style="color:goldenrod">Assisted</span>
Coastal Payroll | `coastal_payroll` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
CognosHR | `cognos_hr` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Collage | `collage` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Commonwealth Payroll & HR | `commonwealth_payroll_hr` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
ConnectPay | `connectpay` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted**</span>
CPM Employer Services iSolved | `cpm_isolved` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Crescent Payroll Solutions | `crescent_payroll_solutions` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
CSC Paymaster | `csc_paymaster` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Darwinbox | `darwinbox` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Decent | `decent` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Deel | `deel` | <span style="color:goldenrod">Assisted*</span> | <span style="color:goldenrod">Assisted</span>
Deltek | `deltek` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Deluxe | `deluxe` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
DM Payroll Solutions | `dm_payroll_solutions` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Dominion Payroll | `dominion_payroll` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Doyle | `doyle_hcm` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Eddy | `eddyhr` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Emplicity | `emplicity` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Employdrive | `employdrive` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
EmPower HR | `empower_hr` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Engage PEO | `engage_peo` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Employer Flexible | `employer_flexible` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Employer Services Corporation (ESC) | `esc` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Everee | `everee` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Evolution Payroll Services | `evolution_payroll_services` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Excel Resources | `excel_resources` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
ExtensisHR | `extensis_hr` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Flock | `flock` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Freshteam | `freshteam` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
FullStack PEO | `fullstack_peo` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
G&A Partners | `gna_partners` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Gig Wage | `gigwage` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Goco | `goco` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
greytHR | `greyt_hr` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
GTM Payroll Services Evolution | `gtm_payroll_services_evolution` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
GTM Payroll Services iSolved | `gtm_payroll_services_isolved` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Heartland | `heartland` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Helpside | `helpside` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Highflyer HR | `highflyer_hr` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Horizons | `horizons` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
HR Cloud | `hrcloud` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
HRO | `hro` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
HROne | `hrone` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Hubstaff | `hubstaff` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Humi | `humi` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
INFINITI HR | `infiniti_hr` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Infor | `infor` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Iris HR | `iris_hr` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
iSolved | `isolved` | <span style="color:goldenrod">Assisted*</span> | <span style="color:goldenrod">Assisted</span>
Kenjo | `kenjo` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Keystone Payroll iSolved | `keystone_isolved` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
mp | `mp` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
MPAY | `mpay` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Multiplier | `multiplier` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Netchex | `netchex` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
NaturalHR | `natural_hr` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Newtek | `newtek` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Nextep | `nextep` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Oasis | `oasis` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Obsidian HR iSolved | `obsidianhr_isolved` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
odoo | `odoo` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
OneSource Payroll | `onesource_payroll` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
OnPay | `onpay` | <span style="color:goldenrod">Assisted*</span> | <span style="color:goldenrod">Assisted</span>
Opolis | `opolis` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Oracle Fusion | `oracle_fusion` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Oracle PeopleSoft | `oracle_peoplesoft` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Panther | `panther` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Paragon Payroll iSolved | `paragon_payroll_isolved` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Patriot | `patriot` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Paycor | `paycor` | <span style="color:goldenrod">Assisted*</span> | <span style="color:goldenrod">Assisted**</span>
Payday Workforce Solutions | `payday_workforce_solutions` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
PayFit | `payfit` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
PayNorthwest | `paynw` | <span style="color:goldenrod">Assisted*</span> | <span style="color:goldenrod">Assisted</span>
PayPro HCS isolved | `paypro_hcs_isolved` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Payroll Network | `payroll_network` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Payroll Office of America | `payroll_office_of_america` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Payroll Plus HCM isolved | `payroll_plus_hcm_isolved` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Payroll Plus HCM Evolution | `payroll_plus_hcm_evolution` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Payroll Solutions | `payroll_solutions` | <span style="color:goldenrod">Assisted*</span> | <span style="color:goldenrod">Assisted</span>
Paytime | `paytime` | <span style="color:goldenrod">Assisted*</span> | <span style="color:goldenrod">Assisted</span>
PayUSA | `pay_usa_inc` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
PCS HCM | `pcs_hcm` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
PeopleForce | `peopleforce` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
PeopleHum | `peoplehum` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
People Lease | `people_lease` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Platinum Group | `platinum_group` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
PrestigePEO | `prestige_peo` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
PrimePay | `primepay` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
PrismHR | `prism_hr` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Proliant | `proliant` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
PropelHR | `propel_hr` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
ProSoftware | `prosoftware` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Proxus HR isolved | `proxus_hr` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Remote | `remote` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Resourcing Edge | `resourcing_edge` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
RMI PEO | `rmi_peo` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Sage Payroll | `sage_payroll` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
SAP SuccessFactors | `successfactors` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Savant HCM Evolution | `savant_hcm_evolution` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Sheakley | `sheakley` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Simploy | `simploy` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Skuad | `skuad` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Solution Services | `solution_services` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Southeast Personnel Leasing | `southeastpersonnel` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
SourceOne | `sourceone` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Strategic Payroll Solutions isolved | `strategic_payroll_solutions_isolved` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
SuitePeople (Oracle NetSuite) | `suite_people` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
SurePayroll | `surepayroll` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
SyncHR | `sync_hr` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Teampay by ADP Run | `adp_teampay` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Teamworks Group | `teamworks` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
The Payroll Company | `the_payroll_company` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Thread HCM | `thread_hcm` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Toast Payroll | `toast_payroll` | <span style="color:goldenrod">Assisted*</span> | <span style="color:goldenrod">Assisted</span>
Trakstar | `trakstar` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
UKG Ready (Kronos) | `ukg_ready` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Uzio | `uzio` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Velocity Global | `velocity_global` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
VensureHR | `vensure_hr` | <span style="color:goldenrod">Assisted*  </span> | <span style="color:goldenrod">Assisted</span>
Vfficient | `vfficient` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Viewpoint HR Management Spectrum | `viewpoint_hr_management_spectrum` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Viewpoint HR Management Vista | `viewpoint_hr_management_vista` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Viventium | `viventium` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Wagepoint | `wagepoint` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
WebHR | `web_hr` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
whirks | `whirks` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Workforce Junction | `workforce_junction` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Worklio | `worklio` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Workplace HCM | `workplace_hcm` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Workzoom | `workzoom` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
wurk | `wurk` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Xenium HR | `xenium_hr` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Xero | `xero` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>
Zoho Payroll | `zoho_payroll` | <span style="color:goldenrod">Assisted</span> | <span style="color:goldenrod">Assisted</span>

**these assisted providers are [**Pay Enabled**](../Product-Guides/Assisted-Connect-Flow.md#for-you), meaning initial connection time for connections that require pay is 14 days instead of 6 weeks*

***these providers are [**Assisted Benefits Enabled**](../Product-Guides/Benefits-API.md#Using-benefit-metadata), meaning Finch has connected to the system already and is configured to support the system, including having mapped the benefits supported in the system*

*†ADP Workforce Now utilizes Auth Fallback and so will function as an Assisted flow in Finch Connect. This means the employer will follow normal Assisted Connect instructions to authorize access. Once the Connect flow is completed, ADP WFN will function as a normal, automated connection with one caveat: until the first Data Sync is completed, Finch will serve a 202 response for any request for ADP WFN data. You will need to opt in to Auth Fallback to utilize the ADP Workforce Now integration. For more information see the [Data Syncs](../Development-Guides/Data-Syncs.md) page.*

<!--
type: tab
title: ATS
-->
<!-- theme: info -->

To enable access to the ATS API, please reach out to your Finch representative.


### API Providers
Display Name | Id | Read
---------|----------|-----
Lever (beta) | `lever`| <span style="color:darkgreen">Automated</span>

> Assisted Connect is not currently available for ATS integrations.

<!-- type: tab-end -->
