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
   - search for a string `Tuesday, September 11, 2001` in your current directory and all other subdirectories by using the - r flag; notice that the current directory is `technical/911report`, and there is no subdirectory, thus only the files in `technical/911report` are searched. 
```python
(base) jyl@Junyues-MacBook-Pro 911report % grep -r "Tuesday, September 11, 2001" *
chapter-1.txt:    Tuesday, September 11, 2001, dawned temperate and nearly cloudless in the eastern United States. Millions of men and women readied themselves for work. Some made their way to the Twin Towers, the signature structures of the World Trade Center complex in New York City. Others went to Arlington, Virginia, to the Pentagon. Across the Potomac River, the United States Congress was back in session. At the other end of Pennsylvania Avenue, people began to line up for a White House tour. In Sarasota, Florida, President George W. Bush went for an early morning run.
```
   - example2:
   - search for a string `THE` in your current directory and all other subdirectories by using the - r flag; notice that the current directory is `technical` thus, all the files in the subdirectories under then `technical` directory are searched recursively 
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
   - example3:
   - to ignore the case sensitivity, we use `-i` flag; notice that if we did not use `-i`, the grep command would only ouput one line, however if we use `-i` flag, turns out there are many lines containing `we have` ignoring case sensitivity.  
```python
(base) jyl@Junyues-MacBook-Pro 911report % grep -i "we have" chapter-1.txt
"WE HAVE SOME PLANES"
    At the same time, Boston Center realized that a message transmitted just before 8:25 by the hijacker pilot of American 11 included the phrase, "We have some planes."
    Because several passengers on United 93 described three hijackers on the plane, not four, some have wondered whether one of the hijackers had been able to use the cockpit jump seat from the outset of the flight. FAA rules allow use of this seat by documented and approved individuals, usually air carrier or FAA personnel. We have found no evidence indicating that one of the hijackers, or anyone else, sat there on this flight. All the hijackers had assigned seats in first class, and they seem to have used them. We believe it is more likely that Jarrah, the crucial pilot-trained member of their team, remained seated and inconspicuous until after the cockpit was seized; and once inside, he would not have been visible to the passengers.
    At 9:32, a hijacker, probably Jarrah, made or attempted to make the following announcement to the passengers of Flight 93:"Ladies and Gentlemen: Here the captain, please sit down keep remaining sitting. We have a bomb on board. So, sit." The flight data recorder (also recovered) indicates that Jarrah then instructed the plane's autopilot to turn the aircraft around and head east.
    At 8:24:38, the following transmission came from American 11: American 11: We have some planes. Just stay quiet, and you'll be okay. We are returning to the airport.
    The controller only heard something unintelligible; he did not hear the specific words "we have some planes." The next transmission came seconds later: American 11: Nobody move. Everything will be okay. If you try to make any moves, you'll endanger yourself and the airplane. Just stay quiet.
    FAA: Hi. Boston Center TMU [Traffic Management Unit], we have a problem here. We have a hijacked aircraft headed towards New York, and we need you guys to, we need someone to scramble some F-16s or something up there, help us out.
    Manager, New York Center: We have several situations going on here. It's escalating big, big time. We need to get the military involved with us. . . . We're, we're involved with something else, we have other aircraft that may have a similar situation going on here.
    Boston Center: . . . as far as the tape, Bobby seemed to think the guy said that "we have planes." Now, I don't know if it was because it was the accent, or if there's more than one, but I'm gonna, I'm gonna reconfirm that for you, and I'll get back to you real quick. Okay? New England Region: Appreciate it.
    Boston Center immediately advised the New England Region that it was going to stop all departures at airports under its control. At 9:05, Boston Center confirmed for both the FAA Command Center and the New England Region that the hijackers aboard American 11 said "we have planes." At the same time, New York Center declared "ATC zero"-meaning that aircraft were not permitted to depart from, arrive at, or travel through New York Center's airspace until further notice.
    Within minutes of the second impact, Boston Center instructed its controllers to inform all aircraft in its airspace of the events in New York and to advise aircraft to heighten cockpit security. Boston Center asked the Herndon Command Center to issue a similar cockpit security alert nationwide. We have found no evidence to suggest that the Command Center acted on this request or issued any type of cockpit security alert.
    By 9:25, FAA's Herndon Command Center and FAA headquarters knew two aircraft had crashed into the World Trade Center. They knew American 77 was lost. At least some FAA officials in Boston Center and the New England Region knew that a hijacker on board American 11 had said "we have some planes." Concerns over the safety of other aircraft began to mount. A manager at the Herndon Command Center asked FAA headquarters if they wanted to order a "nationwide ground stop." While this was being discussed by executives at FAA headquarters, the Command Center ordered one at 9:25.
    FAA: That was another-it was evidently another aircraft that hit the tower. That's the latest report we have.
    The mention of a "third aircraft" was not a reference to American 77. There was confusion at that moment in the FAA. Two planes had struck the World Trade Center, and Boston Center had heard from FAA headquarters in Washington that American 11 was still airborne. We have been unable to identify the source of this mistaken FAA information.
    Right after the Pentagon was hit, NEADS learned of another possible hijacked aircraft. It was an aircraft that in fact had not been hijacked at all. After the second World Trade Center crash, Boston Center managers recognized that both aircraft were transcontinental 767 jetliners that had departed Logan Airport. Remembering the "we have some planes" remark, Boston Center guessed that Delta 1989 might also be hijacked. Boston Center called NEADS at 9:41 and identified Delta 1989, a 767 jet that had left Logan Airport for Las Vegas, as a possible hijack. NEADS warned the FAA's Cleveland Center to watch Delta 1989. The Command Center and FAA headquarters watched it too. During the course of the morning, there were multiple erroneous reports of hijacked aircraft. The report of American 11 heading south was the first; Delta 1989 was the second.
    At 9:32, a third radio transmission came over the frequency:"Keep remaining sitting. We have a bomb on board." The controller understood, but chose to respond: "Calling Cleveland Center, you're unreadable. Say again, slowly." He notified his supervisor, who passed the notice up the chain of command. By 9:34, word of the hijacking had reached FAA headquarters.
    NEADS: When did he land? 'Cause we have got confirmation- FAA: He did not land.
    The President's motorcade departed at 9:35, and arrived at the airport between 9:42 and 9:45. During the ride the President learned about the attack on the Pentagon. He boarded the aircraft, asked the Secret Service about the safety of his family, and called the Vice President. According to notes of the call, at about 9:45 the President told the Vice President:"Sounds like we have a minor war going on here, I heard about the Pentagon. We're at war . . . somebody's going to pay."
    The Vice President remembered placing a call to the President just after entering the shelter conference room. There is conflicting evidence about when the Vice President arrived in the shelter conference room. We have concluded, from the available evidence, that the Vice President arrived in the room shortly before 10:00, perhaps at 9:58. The Vice President recalled being told, just after his arrival, that the Air Force was trying to establish a combat air patrol over Washington.
(base) jyl@Junyues-MacBook-Pro 911report % grep "WE HAVE" chapter-1.txt   
"WE HAVE SOME PLANES"
```
   - example4: 
   - notice that the string is `Addition` with the capital A, but in the output, we have `addition`. Thus we are searching string ignoring case sensitivity. 
```python
    (base) jyl@Junyues-MacBook-Pro 911report % grep -i "Addition" chapter-1.txt
    In passing through these checkpoints, each of the hijackers would have been screened by a walk-through metal detector calibrated to detect items with at least the metal content of a .22-caliber handgun. Anyone who might have set off that detector would have been screened with a hand wand-a procedure requiring the screener to identify the metal item or items that caused the alarm. In addition, an X-ray machine would have screened the hijackers' carry-on belongings. The screening was in place to identify and confiscate weapons and other items prohibited from being carried onto a commercial flight.
    About 20 minutes later, at 7:35, another passenger for Flight 77, Hani Hanjour, placed two carry-on bags on the X-ray belt in the Main Terminal's west checkpoint, and proceeded, without alarm, through the metal detector. A short time later, Nawaf and Salem al Hazmi entered the same checkpoint. Salem al Hazmi cleared the metal detector and was permitted through; Nawaf al Hazmi set off the alarms for both the first and second metal detectors and was then hand-wanded before being passed. In addition, his over-the-shoulder carry-on bag was swiped by an explosive trace detector and then passed. The video footage indicates that he was carrying an unidentified item in his back pocket, clipped to its rim.
    On the morning of 9/11, there were only 37 passengers on United 93-33 in addition to the 4 hijackers. This was below the norm for Tuesday mornings during the summer of 2001. But there is no evidence that the hijackers manipulated passenger levels or purchased additional seats to facilitate their operation.
Military Notification and Response. Boston Center did not follow the protocol in seeking military assistance through the prescribed chain of command. In addition to notifications within the FAA, Boston Center took the initiative, at 8:34, to contact the military through the FAA's Cape Cod facility. The center also tried to contact a former alert site in Atlantic City, unaware it had been phased out. At 8:37:52, Boston Center reached NEADS. This was the first notification received by the military-at any level-that American 11 had been hijacked:
    More than the actual events, inaccurate government accounts of those events made it appear that the military was notified in time to respond to two of the hijackings, raising questions about the adequacy of the response. Those accounts had the effect of deflecting questions about the military's capacity to obtain timely and accurate information from its own sources. In addition, they overstated the FAA's ability to provide the military with timely and useful information that morning.
    When they learned a second plane had struck the World Trade Center, nearly everyone in the White House told us, they immediately knew it was not an accident. The Secret Service initiated a number of security enhancements around the White House complex. The officials who issued these orders did not know that there were additional hijacked aircraft, or that one such aircraft was en route to Washington. These measures were precautionary steps taken because of the strikes in New York.
```
   - example5:
   - to count the total number of lines where the string pattern `addition` appears or resides; we can confirm it is actually 6 lines by looking at example 4
```python
(base) jyl@Junyues-MacBook-Pro 911report % grep -c "addition" chapter-1.txt
6
```
   - example6:
   - to count the total number of lines where the string pattern `Tuesday` appears or resides
```python
(base) jyl@Junyues-MacBook-Pro 911report % grep -c "Tuesday" chapter-1.txt
3
```
   - example 7:
   - To number the lines where the string pattern `addition` is matched
```python
(base) jyl@Junyues-MacBook-Pro 911report % grep -n "addition" chapter-1.txt
30:    In passing through these checkpoints, each of the hijackers would have been screened by a walk-through metal detector calibrated to detect items with at least the metal content of a .22-caliber handgun. Anyone who might have set off that detector would have been screened with a hand wand-a procedure requiring the screener to identify the metal item or items that caused the alarm. In addition, an X-ray machine would have screened the hijackers' carry-on belongings. The screening was in place to identify and confiscate weapons and other items prohibited from being carried onto a commercial flight.
48:    About 20 minutes later, at 7:35, another passenger for Flight 77, Hani Hanjour, placed two carry-on bags on the X-ray belt in the Main Terminal's west checkpoint, and proceeded, without alarm, through the metal detector. A short time later, Nawaf and Salem al Hazmi entered the same checkpoint. Salem al Hazmi cleared the metal detector and was permitted through; Nawaf al Hazmi set off the alarms for both the first and second metal detectors and was then hand-wanded before being passed. In addition, his over-the-shoulder carry-on bag was swiped by an explosive trace detector and then passed. The video footage indicates that he was carrying an unidentified item in his back pocket, clipped to its rim.
170:    On the morning of 9/11, there were only 37 passengers on United 93-33 in addition to the 4 hijackers. This was below the norm for Tuesday mornings during the summer of 2001. But there is no evidence that the hijackers manipulated passenger levels or purchased additional seats to facilitate their operation.
290:Military Notification and Response. Boston Center did not follow the protocol in seeking military assistance through the prescribed chain of command. In addition to notifications within the FAA, Boston Center took the initiative, at 8:34, to contact the military through the FAA's Cape Cod facility. The center also tried to contact a former alert site in Atlantic City, unaware it had been phased out. At 8:37:52, Boston Center reached NEADS. This was the first notification received by the military-at any level-that American 11 had been hijacked:
538:    More than the actual events, inaccurate government accounts of those events made it appear that the military was notified in time to respond to two of the hijackings, raising questions about the adequacy of the response. Those accounts had the effect of deflecting questions about the military's capacity to obtain timely and accurate information from its own sources. In addition, they overstated the FAA's ability to provide the military with timely and useful information that morning.
574:    When they learned a second plane had struck the World Trade Center, nearly everyone in the White House told us, they immediately knew it was not an accident. The Secret Service initiated a number of security enhancements around the White House complex. The officials who issued these orders did not know that there were additional hijacked aircraft, or that one such aircraft was en route to Washington. These measures were precautionary steps taken because of the strikes in New York.
```
   - example8:
   - 
```python

```
* That makes 8 total examples, all focused on a single command. There should be two examples each for four different command-line options. Many commands like these have pretty sophisticated behavior possible – it can take years to be exposed to and learn all of the possible tricks and inner workings.

* Along with each option/mode you show, cite your source for how you found out about it as a URL or a description of where you found it. See the syllabus on Academic Integrity and how to cite sources like ChatGPT for this class.
