using System;
using System.Collections;
using System.Collections.Generic;
using System.ComponentModel;
using System.Configuration;
using System.Data;
using System.Data.OleDb;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Media; //.Media.SystemSound;
using System.Reflection;
using System.Text;
using System.Text.RegularExpressions;
using System.Xml;
using System.Xml.Xsl;
using System.Xml.Linq;
//
using System.Web;
using System.Web.Services;
using System.Web.Services.Protocols;
//
//#################################
using QurnumClass;
//using QrnDrawGrid = QurnumClass.QrnDrawGrid;
//#################################

namespace QuranMlngDg19
{
    /// <summary>
    /// Summary description for QuranServices
    /// </summary>
    [WebService(Namespace = "http://elrazi.azurewebsites.net/QuranMlngDg19/")]  // http://tempuri.org/
    [WebServiceBinding(ConformsTo = WsiProfiles.BasicProfile1_1)]
    [ToolboxItem(false)]
    // To allow this Web Service to be called from javascript, using ASP.NET AJAX, uncomment the following line. 
    [System.Web.Script.Services.ScriptService]
    public class QuranServices : System.Web.Services.WebService
    {
        public QuranServices()
        {
            // Constructor
        }

        /*****************/
        //[WebMethod(EnableSession = true)]
        //[WebMethod]
        [WebMethod(EnableSession = true, Description = "QURAN Searxh Engine By Ayah")]   // this method for expose
        //#########################
        public string SrchQuranByNo(int surahPar, int ayahPar, int tfsrLangPar)
        {

            //########################################################################
            QrnDrawGrid.buildLangshLkUpTbl();
            //########################################################################
            QrnDrawGrid.buildFahrasLkUpTbl();
            //string NoOfAyah = QrnDrawGrid.lookUpTblFahras[i, 7];
            //NoOfAyah = NoOfAyah.Trim();
            //################################  Ibn Kathir
            int actLangNo = tfsrLangPar;
            if (actLangNo < 5)
            {
                actLangNo = 16;
            }
            //########################################################################
            //int ayahPar=1, tfsrLangPar=11;
            string TfsirText = "Nothing";
            string SurahText = "Nothing";
            //################################
            bool responsePar = surahPar > 0;
            //################################
            switch (responsePar)
            {
                case true:
                    SurahText = QrnDrawGrid.readSearchAyah(surahPar + 1000, ayahPar);
                    TfsirText = QrnDrawGrid.readTafseerAyah(surahPar + 1000, ayahPar, actLangNo);// + 5);
                    break;
                default:
                    SurahText = QrnDrawGrid.readSearchAyah(surahPar + 1000, ayahPar);
                    TfsirText = QrnDrawGrid.readTafseerAyah(1001, 1, 16);
                    break;
            }

            //################################
            var JSONAyahSrch = new StringBuilder();
            //var params = "{ surahPar: '" + surahPar + "', ayahPar: '"  + ayahPar + "', tfsrLangPar: '" + tfsrLangPar +  "'}";
            JSONAyahSrch.Append("\n");
            JSONAyahSrch.Append("{\"(");
            JSONAyahSrch.Append(surahPar);
            JSONAyahSrch.Append("/");
            JSONAyahSrch.Append(ayahPar);
            JSONAyahSrch.Append("/");
            JSONAyahSrch.Append(tfsrLangPar);
            JSONAyahSrch.Append(")\":  \"");
            JSONAyahSrch.Append(SurahText);
            JSONAyahSrch.Append("\"}");
            //JSONAyahSrch.Append("           ");
            //JSONAyahSrch.Append("<BR>");
            //JSONAyahSrch.Append("\\n");
            JSONAyahSrch.Append("\n");
            JSONAyahSrch.Append("{\"(");
            JSONAyahSrch.Append(surahPar);
            JSONAyahSrch.Append("/");
            JSONAyahSrch.Append(ayahPar);
            JSONAyahSrch.Append("/");
            JSONAyahSrch.Append(tfsrLangPar);
            JSONAyahSrch.Append(")\":  \"");
            JSONAyahSrch.Append(TfsirText);
            JSONAyahSrch.Append("\"}");
            JSONAyahSrch.Append("\n");
            //################################
            return JSONAyahSrch.ToString();
            //################################
        }
        /*****************/
        //[WebMethod(EnableSession = true)]
        //[WebMethod]
        [WebMethod(EnableSession = true, Description = "QURAN Searxh Engine By Text")]   // this method for expose
        //#########################
        public string SrchQuranByText(string SrchTextPar)//, int tfsrLangPar)//(int tfsrLangPar)//
        {
            //#######################
            //QrnDrawGrid.langRow = 11;
            //if (tfsrLangPar > 5)
                //QrnDrawGrid.langRow = tfsrLangPar - 5;
            //####
            QrnDrawGrid.langRow = 11;
            QrnDrawGrid.selctLangIndx = QrnDrawGrid.langRow + 5;
            //################################
            string wrkSearchText = SrchTextPar.ToString();//"محمد";
            /*//################################
            var JSONSrchArgs = new StringBuilder();
            //var params = "{ surahPar: '" + surahPar + "', ayahPar: '"  + ayahPar + "', tfsrLangPar: '" + tfsrLangPar +  "'}";
            JSONSrchArgs.Append(wrkSearchText);
            JSONSrchArgs.Append(" , ");
            JSONSrchArgs.Append(tfsrLangPar);
            JSONSrchArgs.Append(" , ");
            JSONSrchArgs.Append(QrnDrawGrid.langRow);
            JSONSrchArgs.Append(" , ");
            JSONSrchArgs.Append(QrnDrawGrid.selctLangIndx);
            //################################
            return JSONSrchArgs.ToString();
            
            */
            //#######################
            bool jsonFmt = true;
            //################################
            string JSONSrch = QrnDrawGrid.searchQuranByText(wrkSearchText, jsonFmt);
            QrnDrawGrid.selctLangIndx = QrnDrawGrid.langRow + 5;
            //################################
            var JSONAyahSrch = new StringBuilder();
            //################################
            JSONAyahSrch.Append("[");
            JSONAyahSrch.Append(QrnDrawGrid.dllSearchMaxFound);
            JSONAyahSrch.Append("]");
            JSONAyahSrch.Append("\n");
            JSONAyahSrch.Append(JSONSrch);
            JSONAyahSrch.Append("\n");
            //################################
            return JSONAyahSrch.ToString(); 
            //################################
        }
        //########################################################################
        //########################################################################
        [WebMethod(EnableSession = true, Description = "QURAN Ibn Manzour Translation")]   // this method for expose
        //########################################################################
        public string ibnMnzTransQuran(int surahPar, int ayahPar)
        {

            //########################################################################
            //##
            //InterpretSalaf.SelectedIndex = 0; 
            //int docsType = 0;//InterpretSalaf.SelectedIndex;
            //IbnKathrBtn.Text = QrnDrawGrid.InterpretSalafSearch(QrnDrawGrid.Logon_User_BUs_Indx, docsType, 0);
            //################################   Sudais Sharawy ####################################
            //#########################
            //#########################  Ibn Manzour Arabic Dictionary###################
            QrnDrawGrid.Form_PhoneFl = surahPar;
            QrnDrawGrid.Form_FaxFl = ayahPar;
            //#########################
            //return QrnDrawGrid.Form_PhoneFl.ToString();
            //QrnDrawGrid.IbnManzoorDict();
            //#########################  Ibn Manzour Arabic Dictionary###################
            if (!((QrnDrawGrid.Prev_PhoneFl == QrnDrawGrid.Form_PhoneFl) && (QrnDrawGrid.Prev_FaxFl == QrnDrawGrid.Form_FaxFl)))
            {
                //HttpContext.Current.Response.Write("<script>alert('From Surah: " + Form_PhoneFl + ", Form Ayah: " + Form_FaxFl + "\\n Prev Surah: " + Prev_PhoneFl + ", Prev Ayah: " + Prev_FaxFl + "  ')</script>");
                QuranExtApi.extractIbnManzoor();
                //#########################
                QrnDrawGrid.Prev_PhoneFl = surahPar;// 1001;
                QrnDrawGrid.Prev_FaxFl = ayahPar; // 1001;
                //#########################
            }

            //#############################
            StringBuilder IbnMnzrSb = new StringBuilder();
            //#############################
            string IbnMnzrTextRd = string.Empty;
            string dashStr = QrnDrawGrid.strReptChar('=', 32);
            //#############################
            for (int i = 0; i < QrnDrawGrid.IbnMnzrArraySize; i++)
            {
                //HttpContext.Current.Response.Write("<script>alert('CallLine: " + i + ", Location:: " + QrnDrawGrid.IbnMnzrlookUpTbl[i, j] + "\\n lineCnt: " + IbnMnzrlineCnt[i] + "  ')</script>");
                IbnMnzrTextRd = QuranExtApi.readIbnMnzrDict(QrnDrawGrid.IbnMnzrLineCnt[i], QrnDrawGrid.IbnMnzrColmCnt[i]);
                //HttpContext.Current.Response.Write("<script>alert('CallLine: " + i+1 + ", Location:: " + IbnMnzrlookUpTbl[i, j] + "\\n IbnMnzrTextRd: " + textRd + "  ')</script>");
                //#############################
                //string[] parts = Regex.Split(IbnMnzrTextRd, @"(?<!2),(?!0)");
                //string[] parts = IbnMnzrTextRd.Split(',');
                int firstCommaIndex = IbnMnzrTextRd.IndexOf(',');
                string secondPart = IbnMnzrTextRd.Substring(firstCommaIndex + 1); //a,b,c,d
                //#############################
                //IbnMnzrSb.Append("\n>");
                IbnMnzrSb.Append(secondPart);
                IbnMnzrSb.Append("\n");
                IbnMnzrSb.Append(dashStr);
                IbnMnzrSb.Append("\n");

                //IbnManzTextBox.Text += IbnMnzrSb.ToString();
                //IbnMnzrSb = new StringBuilder();

                //break;

            }

            //################################
            return IbnMnzrSb.ToString();
            //################################
        }
        //########################################################################
    }
}
