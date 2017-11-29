---
title: "Образец технологии веб-служб IXmlSerializable"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0202d3f1-a50b-427d-a5bb-79208b8f1c22
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 72c7e9e1cbf47dd54726a16ddeb58a193d62dc31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="web-services-ixmlserializable-technology-sample"></a><span data-ttu-id="cb26f-102">Образец технологии веб-служб IXmlSerializable</span><span class="sxs-lookup"><span data-stu-id="cb26f-102">Web Services IXmlSerializable Technology Sample</span></span>
[<span data-ttu-id="cb26f-103">Скачать образец</span><span class="sxs-lookup"><span data-stu-id="cb26f-103">Download Sample</span></span>](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/IXmlSerializable.zip.exe)  
  
 <span data-ttu-id="cb26f-104">В этом образце показано, как использовать объект <xref:System.Xml.Serialization.IXmlSerializable> для управления сериализацией пользовательских типов в веб-службах ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cb26f-104">This sample shows how to use <xref:System.Xml.Serialization.IXmlSerializable> to control the serialization of custom types in ASP.NET Web Services.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="cb26f-105">Сборка образца с использованием Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cb26f-105">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="cb26f-106">Откройте [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] и выберите в меню **Файл** пункт **Новый веб-сайт**.</span><span class="sxs-lookup"><span data-stu-id="cb26f-106">Open [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] and select **New Web Site** from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="cb26f-107">В левой области диалогового окна **Новый веб-сайт** выберите нужный язык программирования, а затем в правой области выберите **Веб-служба ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="cb26f-107">In the left pane of the **New Web Site** dialog, select your desired programming language, then from the right pane, select **ASP.NET Web Service**.</span></span>  
  
3.  <span data-ttu-id="cb26f-108">Введите **IXmlSerializable** в качестве имени новой веб-службы.</span><span class="sxs-lookup"><span data-stu-id="cb26f-108">Type **IXmlSerializable** as the name of the new Web service.</span></span>  
  
4.  <span data-ttu-id="cb26f-109">В окне обозревателя решений щелкните правой кнопкой мыши значок файла Service.asmx и выберите команду **Удалить**. Повторите это действие для файла с кодом программной части Service.asmx.</span><span class="sxs-lookup"><span data-stu-id="cb26f-109">In the Solution Explorer window, right-click the icon for Service.asmx and select **Delete**; repeat this step for the Service.asmx codebehind file.</span></span>  
  
5.  <span data-ttu-id="cb26f-110">Щелкните правой кнопкой мыши каталог проекта и выберите пункт **Добавить существующий элемент**.</span><span class="sxs-lookup"><span data-stu-id="cb26f-110">Right-click the project directory and select **Add Existing Item**.</span></span> <span data-ttu-id="cb26f-111">В диалоговом окне перейдите во вложенную папку "Служба" языкового каталога.</span><span class="sxs-lookup"><span data-stu-id="cb26f-111">In the dialog, navigate to the Service subdirectory of the language-specific directory.</span></span>  
  
6.  <span data-ttu-id="cb26f-112">Выберите Service.asmx, затем повторите этот шаг для файла фонового кода Service.asmx.</span><span class="sxs-lookup"><span data-stu-id="cb26f-112">Select Service.asmx, then repeat this step for the Service.asmx codebehind file.</span></span>  
  
7.  <span data-ttu-id="cb26f-113">Откройте [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] и перейдите в каталог, который содержит каталог IXmlSerializable, созданный в шаге 3 выше.</span><span class="sxs-lookup"><span data-stu-id="cb26f-113">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to the directory that contains IXmlSerializable directory that you created in step 3 above.</span></span>  
  
8.  <span data-ttu-id="cb26f-114">Щелкните правой кнопкой мыши значок каталога IXmlSerializable и выберите пункт **Общий доступ и безопасность**.</span><span class="sxs-lookup"><span data-stu-id="cb26f-114">Right-click the icon for the IXmlSerializable directory and select **Sharing and Security**.</span></span>  
  
9. <span data-ttu-id="cb26f-115">На вкладке "Общий доступ в Интернете" выберите **Открыть общий доступ к этой папке** и подтвердите параметры по умолчанию, включая имя IXmlSerializable.</span><span class="sxs-lookup"><span data-stu-id="cb26f-115">In the Web Sharing tab, select **Share this Folder**, and confirm the default settings, including the name IXmlSerializable.</span></span>  
  
10. <span data-ttu-id="cb26f-116">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cb26f-116">Click **OK**.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="cb26f-117">Выполнение образца</span><span class="sxs-lookup"><span data-stu-id="cb26f-117">To run the sample</span></span>  
  
1.  <span data-ttu-id="cb26f-118">Откройте окно браузера и выделите адресную строку.</span><span class="sxs-lookup"><span data-stu-id="cb26f-118">Open a browser window and select its address bar.</span></span>  
  
2.  <span data-ttu-id="cb26f-119">Введите адрес **http://localhost/IXmlSerializable/Service.asmx**.</span><span class="sxs-lookup"><span data-stu-id="cb26f-119">Type **http://localhost/IXmlSerializable/Service.asmx**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb26f-120">См. также</span><span class="sxs-lookup"><span data-stu-id="cb26f-120">See Also</span></span>  
 <xref:System.Xml.Serialization.IXmlSerializable>  
 <xref:System.Xml.Serialization>  
 <xref:System.Xml.XmlConvert>  
 <xref:System.Xml.XmlQualifiedName>  
 <xref:System.Xml.XmlReader>  
 <xref:System.Xml.Schema.XmlSchema>  
 <xref:System.Xml.Schema.XmlSchemaSet>  
 <xref:System.Xml.XmlUrlResolver>  
 <xref:System.Xml.XmlWriter>
