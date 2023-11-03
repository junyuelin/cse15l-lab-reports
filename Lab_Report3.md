## Part 1 - Bugs
Choose one of the bugs from lab 4.
```python
static void reverseInPlace(int[] arr) {
   for(int i = 0; i < arr.length; i += 1) {
     arr[i] = arr[arr.length - i - 1];
   }
 }
```
Provide:
* A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)
```python
 @Test
 public void testReverseInPlace2() {
     int[] input1 = {3,2,1};
     ArrayExamples.reverseInPlace(input1);
     assertArrayEquals(new int[]{1,2,3}, input1);
 }
```
* An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)
```python
@Test
public void testReversed1() {
 int[] input1 = { };
 assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
}
```
* The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
<img width="1011" alt="image" src="https://github.com/junyuelin/cse15l-lab-reports/assets/97243889/d241bc12-e697-4e5d-880d-ad612ae44fd7">
* The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)

before:
```python
static void reverseInPlace(int[] arr) {
   for(int i = 0; i < arr.length; i += 1) {
     arr[i] = arr[arr.length - i - 1];
   }
 }
```
after:
```python
static void reverseInPlace(int[] arr) {
 for(int i = 0; i < arr.length/2; i += 1) {
   int temp = arr[i];
   arr[i] = arr[arr.length - i - 1];
   arr[arr.length - i - 1] = temp;
 }
}
```
Briefly describe why the fix addresses the issue.
The code initially changed the element starting from the left of the list with the element starting from the right, but failed to store the original element from the left, thus if we use the code to reverse array {3,2,1}, it will result in {1,2,1}. When the loop goes past the middle index, the result will become faulty. 

## Part 2 - Researching Commands
* Consider the commands less, find, and grep. Choose one of them. Online, find 4 interesting command-line options or alternate ways to use the command you chose. To find information about the commands, a simple Web search like “find command-line options” will probably give decent results. There is also a built-in command on many systems called man (short for “manual”) that displays information about commands; you can use man grep, for example, to see a long listing of information about how grep works. Also consider asking ChatGPT!

* For example, we saw the -name option for find in class. For each of those options, give 2 examples of using it on files and directories from ./technical. Show each example as a code block that shows the command and its output, and write a sentence or two about what it’s doing and why it’s useful.

source: https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix
   - example1:
```python
(base) jyl@Junyues-MacBook-Pro 911report % grep -r "Tuesday, September 11, 2001" *
chapter-1.txt:    Tuesday, September 11, 2001, dawned temperate and nearly cloudless in the eastern United States. Millions of men and women readied themselves for work. Some made their way to the Twin Towers, the signature structures of the World Trade Center complex in New York City. Others went to Arlington, Virginia, to the Pentagon. Across the Potomac River, the United States Congress was back in session. At the other end of Pennsylvania Avenue, people began to line up for a White House tour. In Sarasota, Florida, President George W. Bush went for an early morning run.
```
```python
(base) jyl@Junyues-MacBook-Pro technical % grep -r "THE" *    
911report/chapter-13.1.txt:            HOW TO DO IT? A DIFFERENT WAY OF ORGANIZING THE GOVERNMENT
911report/chapter-13.1.txt:            UNITY OF EFFORT ACROSS THE FOREIGN-DOMESTIC DIVIDE
911report/chapter-13.1.txt:            UNITY OF EFFORT IN THE INTELLIGENCE COMMUNITY
911report/chapter-13.1.txt:            UNITY OF EFFORT IN THE CONGRESS
911report/chapter-13.1.txt:            ORGANIZING AMERICA'S DEFENSES IN THE UNITED STATES
911report/chapter-3.txt:            FROM THE OLD TERRORISM TO THE NEW: THE FIRST WORLD TRADE CENTER
911report/chapter-3.txt:            ADAPTATION-AND NONADAPTATION-IN THE LAW ENFORCEMENT COMMUNITY
911report/chapter-3.txt:             . . . AND IN THE FEDERAL AVIATION ADMINISTRATION
911report/chapter-3.txt:             . . . AND IN THE INTELLIGENCE COMMUNITY
911report/chapter-3.txt:                entire U.S. intelligence effort. 3.5 . . . AND IN THE STATE DEPARTMENT AND THE
911report/chapter-3.txt:             . . . AND IN THE WHITE HOUSE
911report/chapter-3.txt:             . . . AND IN THE CONGRESS
911report/chapter-3.txt:            BEFORE THE BOMBINGS IN KENYA AND TANZANIA
911report/chapter-2.txt:            THE FOUNDATION OF THE NEW TERRORISM
911report/chapter-2.txt:            BIN LADIN'S APPEAL IN THE ISLAMIC WORLD 
911report/chapter-2.txt:            THE RISE OF BIN LADIN AND AL QAEDA (1988-1992)
911report/chapter-2.txt:            BUILDING AN ORGANIZATION, DECLARING WAR ON THE UNITED STATES
911report/chapter-1.txt:INSIDE THE FOUR FLIGHTS
911report/chapter-5.txt:            AL QAEDA AIMS AT THE AMERICAN HOMELAND
911report/chapter-5.txt:            THE "PLANES OPERATION"
911report/chapter-5.txt:            THE HAMBURG CONTINGENT
911report/chapter-6.txt:            THE MILLENNIUM CRISIS
911report/chapter-6.txt:            THE ATTACK ON THE USS COLE
911report/chapter-6.txt:            THE NEW ADMINISTRATION'S APPROACH
911report/chapter-7.txt:            THE ATTACK LOOMS
911report/chapter-7.txt:            THE 9/11 PILOTS IN THE UNITED STATES
911report/chapter-7.txt:            ASSEMBLING THE TEAMS
911report/chapter-9.txt:            EMERGENCY RESPONSE ATTHE PENTAGON
911report/chapter-8.txt:            "THE SYSTEM WAS BLINKING RED"
911report/chapter-8.txt:            THE SUMMER OF THREAT
911report/chapter-12.txt:            ATTACK TERRORISTS AND THEIR ORGANIZATIONS
911report/chapter-12.txt:            PREVENT THE CONTINUED GROWTH OF ISLAMIST TERRORISM
911report/chapter-10.txt:            "PHASE TWO" AND THE QUESTION OF IRAQ
biomed/gb-2002-3-12-research0083.txt:            [ 3] and PANTHER [ 79].
biomed/1471-2164-2-1.txt:          and THE (0.65%); LTR (0.7%); and the DNA elements MLT
government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt:SUPREME COURT OF THE UNITED STATES
government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt:CERTIORARI TO THE UNITED STATES COURT OF APPEALS FOR THE SECOND
government/About_LSC/Comments_on_semiannual.txt:COMMENTS ON THE OFFICE OF INSPECTOR GENERAL'S SEMIANNUAL REPORT
government/About_LSC/Comments_on_semiannual.txt:TO THE CONGRESS FOR THE PERIOD
government/About_LSC/Comments_on_semiannual.txt:MESSAGE OF THE BOARD OF DIRECTORS
government/About_LSC/Special_report_to_congress.txt:SERVING THE CIVIL LEGAL NEEDS OF LOW-INCOME AMERICANS
government/About_LSC/commission_report.txt:LABOR, REPORT ON THE USE OF TEMPORARY FOREIGN WORKERS IN THE
government/About_LSC/commission_report.txt:IV. CONCLUSION: THE MEANING OF THE PRESENCE REQUIREMENT
government/About_LSC/LegalServCorp_v_VelazquezDissent.txt:SUPREME COURT OF THE UNITED STATES
government/About_LSC/LegalServCorp_v_VelazquezDissent.txt:ON WRITS OF CERTIORARI TO THE UNITED STATES COURT OF APPEALS FOR
government/About_LSC/LegalServCorp_v_VelazquezDissent.txt:THE SECOND CIRCUIT
government/About_LSC/LegalServCorp_v_VelazquezDissent.txt:JUSTICE SCALIA, with whom THE CHIEF JUSTICE, JUSTICE O'CONNOR,
government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt:FOR THE ONTARIO LEGAL AID SPEAKER SERIES
government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt:SUPREME COURT OF THE UNITED STATES
government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt:ON WRITS OF CERTIORARI TO THE UNITED STATES COURT OF APPEALS FOR
government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt:THE SECOND CIRCUIT
government/About_LSC/diversity_priorities.txt:THE NEED FOR A DIVERSE WORKFORCE WITHIN THE LEGAL SERVICES
government/About_LSC/ODonnell_et_al_v_LSCdecision.txt:FOR THE FOURTH CIRCUIT
government/About_LSC/State_Planning_Special_Report.txt:III. AN OVERVIEW OF THE STATE PLANNING PROCESS
government/Env_Prot_Agen/section-by-section_summary.txt:SECTION-BY-SECTION SUMMARY OF THE CLEAR SKIES ACT OF 2002
government/Env_Prot_Agen/ctf7-10.txt:STANDARD, SYNTHETIC DILUTION WATER
government/Env_Prot_Agen/ctf7-10.txt:DEIONIZED WATER USED TO PREPARE STANDARD, SYNTHETIC,
government/Env_Prot_Agen/ctf7-10.txt:STANDARD, SYNTHETIC FRESHWATER
government/Env_Prot_Agen/ctf7-10.txt:TABLE 3. PREPARATION OF SYNTHETIC FRESHWATER USING REAGENT GRADE
government/Env_Prot_Agen/ctf7-10.txt:TABLE 4. PREPARATION OF SYNTHETIC FRESHWATER USING MINERAL
government/Env_Prot_Agen/ctf7-10.txt:THE FOLLOWING EFFLUENT SAMPLING METHODS ARE
government/Env_Prot_Agen/ctf7-10.txt:RELATIONSHIP BETWEEN ENDPOINTS DETERMINED BY HYPOTHESIS
government/Env_Prot_Agen/ctf7-10.txt:9.3.1 HYPOTHESIS TESTS
government/Env_Prot_Agen/ctf7-10.txt:9.4.1 ROLE OF THE STATISTICIAN
government/Env_Prot_Agen/ctf7-10.txt:PLOTTING THE DATA
government/Env_Prot_Agen/ctf7-10.txt:HYPOTHESIS TESTS
government/Env_Prot_Agen/ctf7-10.txt:T TEST WITH THE BONFERRONI ADJUSTMENT
government/Env_Prot_Agen/ctf7-10.txt:WILCOXON RANK SUM TEST WITH THE BONFERRONI
government/Env_Prot_Agen/ctf7-10.txt:A CAUTION IN THE USE OF HYPOTHESIS TESTING
government/Env_Prot_Agen/ctf7-10.txt:SUBLETHAL HYPOTHESIS TESTING ENDPOINTS SUBMITTED UNDER NPDES
government/Env_Prot_Agen/ctf1-6.txt:TRANSPORTATION TO THE TEST SITE
government/Env_Prot_Agen/ro_clear_skies_book.txt:EXECUTIVE SUMMARY - THE CLEAR SKIES INITIATIVE
government/Env_Prot_Agen/ro_clear_skies_book.txt:BACKGROUND � THE SUCCESS OF THE CLEAN AIR ACT
government/Env_Prot_Agen/ro_clear_skies_book.txt:THE CLEAR SKIES INITIATIVE � BUILDING ON THE CLEAN AIR ACT
government/Env_Prot_Agen/ro_clear_skies_book.txt:HOW THE CLEAR SKIES INITIATIVE WORKS
government/Env_Prot_Agen/ro_clear_skies_book.txt:THE CAP AND TRADE SYSTEM IN THE CLEAR SKIES INITIATIVE
government/Env_Prot_Agen/ro_clear_skies_book.txt:WHAT ARE THE RESULTS?
government/Env_Prot_Agen/ro_clear_skies_book.txt:WHAT THE EXPERTS SAY ABOUT THE ACID RAIN CAP AND TRADE
government/Env_Prot_Agen/ctm4-10.txt:TRANSPORTATION TO THE TEST SITE
government/Env_Prot_Agen/ctm4-10.txt:STANDARD, SYNTHETIC DILUTION WATER
government/Env_Prot_Agen/ctm4-10.txt:DEIONIZED WATER USED TO PREPARE STANDARD, SYNTHETIC,
government/Env_Prot_Agen/ctm4-10.txt:STANDARD, SYNTHETIC SEAWATER
government/Env_Prot_Agen/ctm4-10.txt:THE FOLLOWING EFFLUENT SAMPLING METHODS ARE
government/Env_Prot_Agen/ctm4-10.txt:RELATIONSHIP BETWEEN ENDPOINTS DETERMINED BY HYPOTHESIS
government/Env_Prot_Agen/ctm4-10.txt:9.3.1 HYPOTHESIS TESTS
government/Env_Prot_Agen/ctm4-10.txt:9.4.1 ROLE OF THE STATISTICIAN
government/Env_Prot_Agen/ctm4-10.txt:PLOTTING THE DATA
government/Env_Prot_Agen/ctm4-10.txt:ANALYSIS OF THE SEA URCHIN, ARBACIA PUNCTULATA,
government/Env_Prot_Agen/ctm4-10.txt:HYPOTHESIS TESTS
government/Env_Prot_Agen/ctm4-10.txt:T TEST WITH THE BONFERRONI ADJUSTMENT
government/Env_Prot_Agen/ctm4-10.txt:WILCOXON RANK SUM TEST WITH THE BONFERRONI
government/Env_Prot_Agen/ctm4-10.txt:A CAUTION IN THE USE OF HYPOTHESIS TESTING
government/Env_Prot_Agen/ctm4-10.txt:SUBLETHAL HYPOTHESIS TESTING ENDPOINTS SUBMITTED UNDER NPDES
government/Env_Prot_Agen/atx1-6.txt:TRANSPORTATION TO THE TEST SITE
government/Env_Prot_Agen/bill.txt:IN THE XXXXX OF THE UNITED STATES
government/Env_Prot_Agen/bill.txt:OTHER PROVISIONS; ENFORCEMENT.
government/Env_Prot_Agen/bill.txt:TABLE A.- AFFECTED SOURCES AND UNITS IN PHASE I AND THEIR SULFUR
government/Env_Prot_Agen/bill.txt:SEC. 3. OTHER AMENDMENTS.
government/Env_Prot_Agen/tech_adden.txt:TECHNICAL ADDENDUM: METHODOLOGIES FOR THE BENEFIT ANALYSIS OF
government/Env_Prot_Agen/tech_adden.txt:THE CLEAR SKIES INITIATIVE
government/Gen_Account_Office/Testimony_cg00010t.txt:3.1 OTHER1
government/Gen_Account_Office/og97032.txt:ISSUED BY THE DEPARTMENT OF JUSTICE, IMMIGRATION AND NATURALIZATION
government/Gen_Account_Office/og99036.txt:ISSUED BY THE DEPARTMENT OF HEALTH AND HUMAN SERVICES, FOOD AND
government/Gen_Account_Office/og99036.txt:DRUG ADMINISTRATION ENTITLED "OVER-THE-COUNTER HUMAN DRUGS;
government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt:TO AUDIT OFFICIALS AND OTHERS INTERESTED IN GOVERNMENT AUDITING
government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt:CONSIDERING THE RESULTS OF PREVIOUS AUDITS
government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt:REPORTING FRAUD, ILLEGAL ACTS, AND OTHER NONCOMPLIANCE
government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:TRANSACTIONS WITH THE PUBLIC
government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:TRANSACTIONS NOT RECOGNIZED AS REVENUES, GAINS, OR OTHER
government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:STEWARDSHIP AND THE REPORTING OBJECTIVES
government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:THE NATURE OF STEWARDSHIP REPORTING
government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:ISSUES FOR WHICH CHANGES WERE MADE TO THE PROPOSED STANDARDS
government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:REPORTING OF INFORMATION NOT SPECIFICALLY ADDRESSED IN THE
government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:OTHER CURRENT LIABILITIES ...............228 ........
government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:OTHER FINANCING SOURCES ................530 .......... S7P70-75
government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:OTHER RETIREMENT BENEFITS ..............423 .......... S5P79-93
government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:OTHER POSTEMPLOYMENT BENEFITS .........428 .......... S5P94-96
government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:OTHER POSTEMPLOYMENT BENEFITS (OPEB) - Forms of benefits
government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:OTHER FINANCING SOURCES - Inflows of resources that increase net
government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:OTHER RETIREMENT BENEFITS (ORB) - Forms of benefits, other than
government/Gen_Account_Office/og97019.txt:ISSUED BY THE FEDERAL COMMUNICATIONS COMMISSION ENTITLED
government/Gen_Account_Office/og97019.txt:"UNLICENSED NII DEVICES IN THE 5 GHZ FREQUENCY RANGE" (ET Docket
government/Gen_Account_Office/og97020.txt:ISSUED BY THE SECURITIES AND EXCHANGE COMMISSION ENTITLED
government/Gen_Account_Office/og97023.txt:ISSUED BY THE SOCIAL SECURITY ADMINISTRATION ENTITLED "SUPPLEMENTAL
government/Gen_Account_Office/og97051.txt:ISSUED BY THE DEPARTMENT OF HEALTH AND HUMAN SERVICES, FOOD AND
government/Gen_Account_Office/og97045.txt:ISSUED BY THE ENVIRONMENTAL PROTECTION AGENCY ENTITLED "NEW MOTOR
government/Gen_Account_Office/Testimony_d01609t.txt:TO THE CONGRESS
government/Gen_Account_Office/og97050.txt:ISSUED BY THE DEPARTMENT OF AGRICULTURE, COMMODITY CREDIT
government/Gen_Account_Office/og96038.txt:ISSUED BY THE DEPARTMENT OF HEALTH AND HUMAN SERVICES, FOOD AND
government/Gen_Account_Office/og96038.txt:DRUG ADMINISTRATION ENTITLED "REGULATIONS RESTRICTING THE SALE AND
government/Gen_Account_Office/og98029.txt:ISSUED BY THE FEDERAL COMMUNICATIONS COMMISSION ENTITLED "SERVICE
government/Gen_Account_Office/og98029.txt:AND AUCTION RULES FOR THE 38.6-40.0 GHZ FREQUENCY BAND" (ET Docket
government/Gen_Account_Office/og96012.txt:ISSUED BY THE FEDERAL ENERGY REGULATORY COMMISSION ENTITLED "OPEN
government/Gen_Account_Office/og97046.txt:ISSUED BY THE SECURITIES AND EXCHANGE COMMISSION ENTITLED "RULES
government/Gen_Account_Office/og97046.txt:IMPLEMENTING AMENDMENTS TO THE INVESTMENT ADVISERS ACT OF 1940
government/Gen_Account_Office/og97052.txt:ISSUED BY THE DEPARTMENT OF AGRICULTURE, ANIMAL AND PLANT HEALTH
government/Gen_Account_Office/og97043.txt:ISSUED BY THE DEPARTMENT OF AGRICULTURE, ANIMAL AND PLANT HEALTH
government/Gen_Account_Office/og96028.txt:ISSUED BY THE FEDERAL COMMUNICATIONS COMMISSION ENTITLED
government/Gen_Account_Office/og96014.txt:ISSUED BY THE FEDERAL COMMUNICATIONS COMMISSION ENTITLED
government/Gen_Account_Office/og96014.txt:AMENDMENT TO THE COMMISSION'S RULES REGARDING A PLAN FOR SHARING
government/Gen_Account_Office/og96014.txt:THE COST OF MICROWAVE RELOCATION, FIRST REPORT AND ORDER AND
government/Gen_Account_Office/og96014.txt:FURTHER NOTICE OF PROPOSED RULE MAKING (WT Docket No. 95-157, FCC
government/Gen_Account_Office/og97041.txt:ISSUED BY THE ENVIRONMENTAL PROTECTION AGENCY ENTITLED "ADDITION OF
government/Gen_Account_Office/og97041.txt:OTHERWISE USE; TOXIC RELEASE INVENTORY; COMMUNITY RIGHT-TO-KNOW"
government/Gen_Account_Office/og96015.txt:ISSUED BY THE BOARD OF GOVERNORS OF THE FEDERAL RESERVE SYSTEM
government/Gen_Account_Office/og96031.txt:ISSUED BY THE DEPARTMENT OF AGRICULTURE, FOOD SAFETY AND INSPECTION
government/Gen_Account_Office/og96033.txt:THE DEPARTMENT OF HOUSING AND URBAN DEVELOPMENT (HUD)
government/Gen_Account_Office/og96027.txt:ISSUED BY THE ENVIRONMENTAL PROTECTION AGENCY ENTITLED "REGULATION
government/Gen_Account_Office/og98022.txt:ISSUED BY THE DEPARTMENT OF THE TREASURY, INTERNAL REVENUE SERVICE;
government/Gen_Account_Office/og98022.txt:THE DEPARTMENT OF LABOR, PENSION AND WELFARE BENEFITS
government/Gen_Account_Office/og98022.txt:ADMINISTRATION; AND THE DEPARTMENT OF HEALTH AND HUMAN SERVICES,
government/Gen_Account_Office/og96026.txt:ISSUED BY THE ENVIRONMENTAL PROTECTION AGENCY (EPA) ENTITLED
government/Gen_Account_Office/og96026.txt:ANNUALIZED NET COSTS AND BENEFITS OF THE FINAL RULE
government/Gen_Account_Office/og96032.txt:ISSUED BY THE FEDERAL COMMUNICATIONS COMMISSION ENTITLED "FIRST
government/Gen_Account_Office/og96036.txt:ISSUED BY THE FEDERAL COMMUNICATIONS COMMISSION ENTITLED "ACCESS TO
government/Gen_Account_Office/og96022.txt:ISSUED BY THE DEPARTMENT OF HOUSING AND URBAN DEVELOPMENT (HUD)
government/Gen_Account_Office/og96022.txt:ENTITLED "AMENDMENTS TO REGULATION X, THE REAL ESTATE SETTLEMENT
government/Gen_Account_Office/og96023.txt:ISSUED BY THE DEPARTMENT OF THE INTERIOR, BUREAU OF INDIAN AFFAIRS
government/Gen_Account_Office/og96023.txt:AND THE DEPARTMENT OF HEALTH AND HUMAN SERVICE, INDIAN HEALTH
government/Gen_Account_Office/og96023.txt:SERVICE ENTITLED "CONTRACTS UNDER THE INDIAN SELF-DETERMINATION AND
government/Gen_Account_Office/og96037.txt:ISSUED BY THE FEDERAL COMMUNICATIONS COMMISSION ENTITLED "POLICIES
government/Gen_Account_Office/og98032.txt:ISSUED BY THE DEPARTMENT OF AGRICULTURE, FOOD AND CONSUMER SERVICE,
government/Gen_Account_Office/og98026.txt:ISSUED BY THE FEDERAL COMMUNICATIONS COMMISSION ENTITLED
government/Gen_Account_Office/og98030.txt:ISSUED BY THE DEPARTMENT OF HEALTH AND HUMAN SERVICES, HEALTH CARE
government/Gen_Account_Office/og98030.txt:SALARY EQUIVALENCY GUIDELINES FOR PHYSICAL THERAPY, RESPIRATORY
government/Gen_Account_Office/og98030.txt:THERAPY, SPEECH LANGUAGE PATHOLOGY, AND OCCUPATIONAL THERAPY
government/Gen_Account_Office/og98024.txt:ISSUED BY THE DEPARTMENT OF LABOR, OCCUPATIONAL SAFETY AND HEALTH
government/Gen_Account_Office/og96021.txt:ANALYSIS OF AMENDMENT OF PARTS 2 AND 15 OF THE COMMISSION'S
government/Gen_Account_Office/og96021.txt:RULES TO DEREGULATE THE EQUIPMENT AUTHORIZATION REQUIREMENTS FOR
government/Gen_Account_Office/og98018.txt:ISSUED BY THE FEDERAL COMMUNICATIONS COMMISSION ENTITLED
government/Gen_Account_Office/og98018.txt:SERVICE IN THE UNITED STATES" (IB Docket No. 96-111; CC Docket No.
government/Gen_Account_Office/og96034.txt:ISSUED BY THE FEDERAL COMMUNICATIONS COMMISSION ENTITLED "REVISION
government/Gen_Account_Office/og96034.txt:OF THE COMMISSION'S RULES TO ENSURE COMPATIBILITY WITH ENHANCED 911
government/Gen_Account_Office/og98019.txt:ISSUED BY THE FEDERAL COMMUNICATIONS COMMISSION ENTITLED "FOREIGN
government/Gen_Account_Office/og98019.txt:PARTICIPATION IN THE U.S. TELECOMMUNICATIONS MARKET" (IB Docket No.
government/Gen_Account_Office/og96020.txt:ISSUED BY THE DEPARTMENT OF VETERANS AFFAIRS ENTITLED "COMPENSATION
government/Gen_Account_Office/og96047.txt:RULES ISSUED BY THE DEPARTMENT OF AGRICULTURE, FEDERAL CROP
government/Gen_Account_Office/og98041.txt:ISSUED BY THE DEPARTMENT OF HEALTH AND HUMAN SERVICES, HEALTH
government/Gen_Account_Office/og97038.txt:ISSUED BY THE DEPARTMENT OF HEALTH AND HUMAN SERVICES ENTITLED
government/Gen_Account_Office/og97038.txt:TO INDIVIDUAL COVERAGE; FEDERAL RULES FOR ACCESS IN THE INDIVIDUAL
government/Gen_Account_Office/Paper_Walker11-2002_acpro122.txt:LEGAL, FINANCIAL AND OTHER ADVISORS:
government/Gen_Account_Office/og97011.txt:ISSUED BY THE SECURITIES AND EXCHANGE COMMISSION ENTITLED
government/Gen_Account_Office/og97039.txt:ISSUED BY THE DEPARTMENT OF TREASURY, INTERNAL REVENUE SERVICE;
government/Gen_Account_Office/og97039.txt:AND THE DEPARTMENT OF HEALTH AND HUMAN SERVICES, HEALTH CARE
government/Gen_Account_Office/og98040.txt:ISSUED BY THE SECURITIES AND EXCHANGE COMMISSION ENTITLED
government/Gen_Account_Office/og96045.txt:ISSUED BY THE ENVIRONMENTAL PROTECTION AGENCY ENTITLED "CONTROL OF
government/Gen_Account_Office/og98044.txt:ISSUED BY THE DEPARTMENT OF HEALTH AND HUMAN SERVICES, HEALTH CARE
government/Gen_Account_Office/og96041.txt:ISSUED BY THE HEALTH CARE FINANCING ADMINISTRATION, DEPARTMENT OF
government/Gen_Account_Office/og96041.txt:THE HOSPITAL INPATIENT PROSPECTIVE PAYMENT SYSTEMS AND FISCAL YEAR
government/Gen_Account_Office/og97001.txt:ISSUED BY THE DEPARTMENT OF AGRICULTURE ENTITLED "FOOD STAMP
government/Gen_Account_Office/og97028.txt:ISSUED BY THE BOARD OF GOVERNORS OF THE FEDERAL RESERVE SYSTEM
government/Gen_Account_Office/og96040.txt:ISSUED BY THE FEDERAL COMMUNICATIONS COMMISSION ENTITLED "FLEXIBLE
government/Gen_Account_Office/og96040.txt:SERVICE OFFERINGS IN THE COMMERCIAL MOBILE RADIO SERVICES" (WT
government/Gen_Account_Office/og98045.txt:ISSUED BY THE ENVIRONMENTAL PROTECTION AGENCY ENTITLED "NATIONAL
government/Gen_Account_Office/og96042.txt:ISSUED BY THE ENVIRONMENTAL PROTECTION AGENCY ENTITLED "FINAL
government/Gen_Account_Office/og96042.txt:REGULATIONS FOR REVISIONS TO THE FEDERAL TEST PROCEDURE FOR
government/Gen_Account_Office/og97002.txt:ISSUED BY THE DEPARTMENT OF AGRICULTURE ENTITLED "CERTIFICATION
government/Gen_Account_Office/og97002.txt:PROVISIONS OF THE MICKEY LELAND CHILDHOOD HUNGER RELIEF ACT"
government/Gen_Account_Office/og97003.txt:ISSUED BY THE DEPARTMENT OF HEALTH AND HUMAN SERVICES, FOOD AND
government/Gen_Account_Office/og96043.txt:RULE) (RIN: 3235-AG66) ISSUED BY THE SECURITIES AND EXCHANGE
government/Gen_Account_Office/og98046.txt:ISSUED BY THE ENVIRONMENTAL PROTECTION AGENCY ENTITLED "EMISSION
government/Post_Rate_Comm/Cohenetal_CreamSkimming.txt:AN ANALYSIS OF THE POTENTIAL FOR CREAM SKIMMING IN THE U.S.
government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt:5. INTERACTION OF THE COST DRIVERS
government/Post_Rate_Comm/Cohenetal_Cost_Function.txt:2. THE COST MODEL
government/Post_Rate_Comm/Cohenetal_Cost_Function.txt:CONFIRMING THE HYPOTHESIS
government/Post_Rate_Comm/Redacted_Study.txt:EFFECT OF REPLACING TERMINAL DUES WITH DOMESTIC POSTAGE ON THE
government/Post_Rate_Comm/Redacted_Study.txt:FINANCES OF INDUSTRIALIZED AND DEVELOPING COUNTRIES AND THE POSTAL
government/Post_Rate_Comm/Cohenetal_Scale.txt:PUBLISHED IN MANAGING CHANGE IN THE POSTAL DELIVERY INDUSTRIES,
government/Post_Rate_Comm/Cohenetal_Scale.txt:THE VIEWS EXPRESSED IN THIS PAPER ARE THOSE OF THE AUTHORS AND
government/Post_Rate_Comm/Cohenetal_Scale.txt:DO NOT NECESSARILY REPRESENT THE OPINIONS OF THE POSTAL RATE
government/Post_Rate_Comm/Cohenetal_Scale.txt:COMMISSION OR THE ENVIRONMENTAL PROTECTION AGENCY. MR. CHU WAS A
government/Post_Rate_Comm/Cohenetal_Scale.txt:PROFESSIONAL STAFF MEMBER OF THE POSTAL RATE COMMISSION FROM
government/Post_Rate_Comm/Cohenetal_RuralDelivery.txt:RURAL DELIVERY AND THE UNIVERSAL SERVICE OBLIGATION: A
government/Post_Rate_Comm/ReportToCongress2002WEB.txt:REPORT TO THE CONGRESS:
government/Post_Rate_Comm/ReportToCongress2002WEB.txt:AUTHORITY OF THE UNITED STATES POSTAL SERVICE TO INTRODUCE NEW
government/Post_Rate_Comm/ReportToCongress2002WEB.txt:REPORT TO THE CONGRESS:
```
* That makes 8 total examples, all focused on a single command. There should be two examples each for four different command-line options. Many commands like these have pretty sophisticated behavior possible – it can take years to be exposed to and learn all of the possible tricks and inner workings.

* Along with each option/mode you show, cite your source for how you found out about it as a URL or a description of where you found it. See the syllabus on Academic Integrity and how to cite sources like ChatGPT for this class.
