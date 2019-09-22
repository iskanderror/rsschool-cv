#Junior Frontend Developer
---
##Contact details
* Name: **Aleksandr Nekrytov**
* Age: **28**
* Location: **Ufa**
* Phone: **+7 (917) 455-32-78**
* E-mail: **iskanderror@gmail.com**

##Summary
Currently I am working as SCADA developer. I developed and implemented many of automation systems 
in oil and gas industry. Rapid development of cloud platforms drives me to improve my frontend development skills.

##Skills
* PLC programming and SCADA development (mostly Schneider Electric & Siemens solutions)
* Databases: MS SQL Server
* Programming: C#, HTML, CSS

##Code Examples

This example is written in Control (Simatic WinCC OA built-in language, similar with C++)

``` c++
/* Main class for Parameter-Value table */
class DataTable
{
  protected dyn_string parameterDps;
  protected dyn_langString  parameterDescriptions;
  protected mixed values = makeDynMixed();
  protected dyn_string foreColorValues;
  protected dyn_string backColorValues;
  protected int count;
  protected shape parentPanel;

  /** Fill class data with information.
    @param dpNameList - initial data for parameterDps array
    @param panelShape - panel, where data will be displayed.
  */
  public int init(dyn_string dpNameList, shape panelShape=0)
  {
    clearData();
    parentPanel = panelShape;
    int dpNameListLen = dynlen(dpNameList);
    for(int i=1; i<= dpNameListLen; i++)
    {
      string dpName = dpNameList[i];
      string query = buildDataQuery(dpName);
      dyn_dyn_anytype tab;
      dpQuery(query,tab);
      count = fillArrays(tab);
    }
    reloadPanel();
    return count;
  }

  /** Make subscription on parameterDps  */
  public void subscribe()
  {
    for(int i=1; i<= count; i++)
    {
      string dpName = parameterDps[i];
      string query = buildSubscriptionQuery(dpName);
      dpQueryConnectSingle("updateArraysCB",false, "", query);
    }
  }

  /** Write new values of into the database
    @param parameterDpsList - list of Dps to dpSet() command
    @param newValues - new values of dps in parameterDpsList
  */
  public int applyChanges(dyn_string parameterDpsList, dyn_anytype newValues)
  {
    return 0;// override this in the derived class
  }
/*... some additional code here ...*/
}; 
```

##Experience
My current responsibilities as head of SCADA development department at NGP Inform are management of the SCADA development team.

My previous experience is available at [LinkedIn](https://www.linkedin.com/in/aleksandr-nekrytov-68607b123/ "Aleksandr Nekrytov")

##Education
* 2019 - HTML Academy ([Profile](https://htmlacademy.ru/profile/id1042307 "Aleksandr Nekrytov"))
* 2018 - Simatic PCS7 course
* 2017 - Wonderware Application Developer
* 2016 - Schneider Electric PlantStruXure Certified Expert
* 2014 - Genesis64 Advanced AnalytiX course
* 2007-2012 - Ufa State Aviation Technical University, Engineer's degree, Applied Mathematics

##English
Pre-Intermediate (A2)