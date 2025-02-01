SOAP-API-WSDL-Method:

El-Razi Company – Canada,  have developed a web service languages, specification (WSDL). Calling this WSDL will help you in developing a new Search-Engine for Quran-by-49-languages. This WSDLS includes WEB-METHODS-API, which you can call the to search QURAN-BY-49-Languages by Text (i.e QuranSrchByText.html) or Verse-No (i.e. QuranSrchByNo.html). Also, you will get interpretation in IBN-Katheer, IBN-Manzour. You will achieve an output in XML and JSON-FORMAT to be using by REST-API, when consuming WSDL/ web-service.

 

The WSDLS WEB-METHODS-API,  can be called by Java, .NET-C# or PYTHON which enable you to search QURAN-BY-49-Languages by text or verse no. including translation in English or IBN-Manzour. These WSDL-API, can be called to achieve results that will be utilized by Facebook, …, etc. For test-case I included in this link, sample HTML pages that provide access WSDLS, The following calls to this WSDLS using HTML with assistance, of JQUERY, JavaScript and AJAX.

WSDL:

http://elrazi.azurewebsites.net/Quran/QuranServices.asmx?WSDL

In HTML-text Format:

http://elrazi.azurewebsites.net/Quran/QuranServices.wsdl

The following calls to this WSDLS using HTML with assistance, of JQUERY, Javascript and AJAX

Quran-search engine by 49-languages by TEXT:

http://elrazi.azurewebsites.net/Quran/QuranSrchByText.html

Quran-search engine by 49-languages by VERSE-No:

http://elrazi.azurewebsites.net/Quran/QuranSrchByNo.html

From the search results, you will be able to get the chapters and verses for the selected language. You will achieve an output in XML and  JSON-FORMAT to be using by REST-API, when consuming WSDL/ web-service.


Quran49LangSrch

Quran by 49-languages Reviewed and Searched http://elrazi.azurewebsites.net/Quran/

El-Razi Company – Canada, please to present to Muslims Community a QURAN program launched at Microsoft AZURE-Protected-WebSite. 
A program reviewed and searched Quran by 49-languages with assistance of searching Arabic Tongue by Ibn-Manzour. 
These programs are in a bilingual manner using Arabic/English, and automatic be loaded and suited on PC/Mobile, they are published at these locations:

Quran Search Engine by 49-Languages Reviewing Chapters

Testing Webservice WSDL

QuranServices


The following operations are supported. For a formal definition, please review the Service Description.

•	SrchQuranByText
QURAN Searxh Engine By Text


QuranServices Testing SrchQuranByText


Click here for a complete list of operations.
SrchQuranByText
QURAN Searxh Engine By Text
Test
The test form is only available for requests from the local machine.
SOAP 1.1
The following is a sample SOAP 1.1 request and response. The placeholders shown need to be replaced with actual values.
POST /Quran/QuranServices.asmx HTTP/1.1
Host: elrazi.azurewebsites.net
Content-Type: text/xml; charset=utf-8
Content-Length: length
SOAPAction: "http://elrazi.azurewebsites.net/QuranMlngDg19/SrchQuranByText"

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Body>
    <SrchQuranByText xmlns="http://elrazi.azurewebsites.net/QuranMlngDg19/">
      <SrchTextPar>string</SrchTextPar>
    </SrchQuranByText>
  </soap:Body>
</soap:Envelope>
HTTP/1.1 200 OK
Content-Type: text/xml; charset=utf-8
Content-Length: length

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Body>
    <SrchQuranByTextResponse xmlns="http://elrazi.azurewebsites.net/QuranMlngDg19/">
      <SrchQuranByTextResult>string</SrchQuranByTextResult>
    </SrchQuranByTextResponse>
  </soap:Body>
</soap:Envelope>
SOAP 1.2
The following is a sample SOAP 1.2 request and response. The placeholders shown need to be replaced with actual values.
POST /Quran/QuranServices.asmx HTTP/1.1
Host: elrazi.azurewebsites.net
Content-Type: application/soap+xml; charset=utf-8
Content-Length: length

<?xml version="1.0" encoding="utf-8"?>
<soap12:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap12="http://www.w3.org/2003/05/soap-envelope">
  <soap12:Body>
    <SrchQuranByText xmlns="http://elrazi.azurewebsites.net/QuranMlngDg19/">
      <SrchTextPar>string</SrchTextPar>
    </SrchQuranByText>
  </soap12:Body>
</soap12:Envelope>
HTTP/1.1 200 OK
Content-Type: application/soap+xml; charset=utf-8
Content-Length: length

<?xml version="1.0" encoding="utf-8"?>
<soap12:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap12="http://www.w3.org/2003/05/soap-envelope">
  <soap12:Body>
    <SrchQuranByTextResponse xmlns="http://elrazi.azurewebsites.net/QuranMlngDg19/">
      <SrchQuranByTextResult>string</SrchQuranByTextResult>
    </SrchQuranByTextResponse>
  </soap12:Body>
</soap12:Envelope>




http://elrazi.azurewebsites.net/Quran/QuranSrch49Lang.html

The above web link represents a solution for the Quran Search Engine in 49 languages. The Quran Search Engine is a means for identifying 
different interpretations of language, recitation by Alsudais and interpretation by Sharawi , Ibn Kathir, Tabary and others..

