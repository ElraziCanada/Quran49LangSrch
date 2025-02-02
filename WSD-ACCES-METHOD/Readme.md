Quran by 49-languages Reviewed and Searched http://elrazi.azurewebsites.net/Quran/

SOAP-API-WSDL-Method:
http://elrazi.azurewebsites.net/Quran/QuranServices.asmx?WSDL


El-Razi Company – Canada,  have developed a web service languages, specification (WSDL), which you can use to call it for any purpose, including Facebook. Here are sample HTML pages that provide access WSDLS. The WSDLS can be called by Java, .NET-C# or PYTHON which enable you to search QURAN-BY-49-Languages by text or verse no. including translation in English or IBN-Manzour.

El-Razi Company – Canada, please to present to Muslims Community a QURAN program launched at Microsoft AZURE-Protected-WEBSite. Also, the company provide WSDLS-SOAP-API,  which will enable users through the call of WSDL-METHODS to get the chapters and verses for the selected language. Also, you will get interpretation in IBN-Katheer, IBN-Manzour. You will achieve an output in XML and JSON-FORMAT to be using by REST-API, when consuming WSDL/ web-service.

QuranServices


The following operations are supported. For a formal definition, please review the Service Description.
•	SrchQuranBy:  QURAN Search Engine By  By Verse No

http://elrazi.azurewebsites.net/Quran/QuranServices.asmx?op=SrchQuranByNo

•	SrchQuranByText: QURAN Search Engine By Text in any Langauge

http://elrazi.azurewebsites.net/Quran/QuranServices.asmx?op=SrchQuranByText

•	ibnMnzTransQuran:   QURAN Ibn Manzour Arabic Tongue Translation 

http://elrazi.azurewebsites.net/Quran/QuranServices.asmx?op=ibnMnzTransQuran


                                   ................................................     

QuranServices for SrchQuranByNo

http://elrazi.azurewebsites.net/QuranMlngDg19/SrchQuranByNo

The following operations are supported. For a formal definition, please review the Service Description.

• SrchQuranByNo

QURAN Searxh Engine By Ayah

QuranServices Testing SrchQuranByNo

Click here for a complete list of operations.

SrchQuranByNo - QURAN Searxh Engine By Ayah

Test

The test form is only available for requests from the local machine.

                                   ................................................     
SOAP Request

The following is a sample SOAP 1.1 request and response. The placeholders shown need to be replaced with actual values.

POST /Quran/QuranServices.asmx HTTP/1.1

Host: elrazi.azurewebsites.net

Content-Type: text/xml; charset=utf-8

Content-Length: length

SOAPAction: "http://elrazi.azurewebsites.net/QuranMlngDg19/SrchQuranByNo"

<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">

soap:Body

<SrchQuranByNo xmlns="http://elrazi.azurewebsites.net/QuranMlngDg19/">

  <surahPar>int</surahPar>
  
  <ayahPar>int</ayahPar>
  
  <tfsrLangPar>int</tfsrLangPar>
  
</SrchQuranByNo>
</soap:Body>

</soap:Envelope>

                                   ................................................     
SOAP Responses:

The response is text containing the verse and translation in the chosen language

<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">

soap:Body

<SrchQuranByNoResponse xmlns="http://elrazi.azurewebsites.net/QuranMlngDg19/">

  <SrchQuranByNoResult>string</SrchQuranByNoResult>
  
</SrchQuranByNoResponse>
</soap:Body>

</soap:Envelope>

                                   ................................................     

Quran-search engine by 49-languages by TEXT:

http://elrazi.azurewebsites.net/Quran/QuranSrchByText.html

Quran-search engine by 49-languages by VERSE-No:

http://elrazi.azurewebsites.net/Quran/QuranSrchByNo.html

From the search results, you will be able to get the chapters and verses for the selected language. You will achieve an output in XML and JSON-FORMAT to be using by REST-API, when consuming WSDL/ web-service.

                                   ................................................     
Testing Webservice WSDL

Quran-Services (WSDSL)

The following operations are supported. For a formal definition, please review the Service Description.

Testing SrchQuranByText - QURAN Search Engine By Text

http://elrazi.azurewebsites.net/QuranMlngDg19/SrchQuranByText

                                   ................................................     
Click here for a complete list of operations, for SrchQuranByText, QURAN Search Engine By Text. The test form is only available for requests from the local machine.

SOAP - Request

The following is a sample SOAP 1.1 request and response. The placeholders shown need to be replaced with actual values.

POST /Quran/QuranServices.asmx HTTP/1.1

Host: elrazi.azurewebsites.net

Content-Type: text/xml; charset=utf-8

Content-Length: length

SOAPAction: "http://elrazi.azurewebsites.net/QuranMlngDg19/SrchQuranByText"

WSDL-REquest-ResponseLAYOUT

<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">

soap:Body

<SrchQuranByText xmlns="http://elrazi.azurewebsites.net/QuranMlngDg19/">

  <SrchTextPar>string</SrchTextPar>
</SrchQuranByText>
</soap:Body>

</soap:Envelope>

                                   ................................................     
SOAP - Response:

The response is text containing the verse and translation in the chosen language

<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">

soap:Body

<SrchQuranByTextResponse xmlns="http://elrazi.azurewebsites.net/QuranMlngDg19/">

  <SrchQuranByTextResult>string</SrchQuranByTextResult>
  
</SrchQuranByTextResponse>
</soap:Body>

</soap:Envelope>

                                   ................................................     

QURAN Ibn Manzour Arabic Tongue Translation

Test

The test form is only available for requests from the local machine.

SOAP Request

The following is a sample SOAP 1.1 request and response. The placeholders shown need to be replaced with actual values.

POST /Quran/QuranServices.asmx HTTP/1.1

Host: elrazi.azurewebsites.net

Content-Type: text/xml; charset=utf-8

Content-Length: length

SOAPAction: "http://elrazi.azurewebsites.net/QuranMlngDg19/ibnMnzTransQuran"

                                   ................................................     

<?xml version="1.0" encoding="utf-8"?>

<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">

  <soap:Body>
  
    <ibnMnzTransQuran xmlns="http://elrazi.azurewebsites.net/QuranMlngDg19/">
    
      <surahPar>int</surahPar>
      
      <ayahPar>int</ayahPar>
      
    </ibnMnzTransQuran>
    
  </soap:Body>
  
</soap:Envelope>


                                   ................................................     

SOAP Response

                                   ................................................     

<?xml version="1.0" encoding="utf-8"?>

<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">

  <soap:Body>
  
    <ibnMnzTransQuranResponse xmlns="http://elrazi.azurewebsites.net/QuranMlngDg19/">
    
      <ibnMnzTransQuranResult>string</ibnMnzTransQuranResult>
      
    </ibnMnzTransQuranResponse>
    
  </soap:Body>
  
</soap:Envelope>

                                   ................................................     

