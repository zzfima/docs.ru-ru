---
title: "Файл, указанный в параметре FileName не является допустимым файлом XML | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8b46b9d896f0dce401992e8a20e040b85091ba5d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a><span data-ttu-id="ed789-102">Файл, указанный в FileName, не является допустимым XML-файлом</span><span class="sxs-lookup"><span data-stu-id="ed789-102">File specified in FileName is not a valid XML file</span></span>
<span data-ttu-id="ed789-103">Указанное имя файла не представляет допустимый XML-файл.</span><span class="sxs-lookup"><span data-stu-id="ed789-103">The file name that you supplied is not a valid XML file.</span></span> <span data-ttu-id="ed789-104">Чтобы задать допустимую структуру и содержимое XML-документа, можно использовать схему DTD, Microsoft XML-Data Reduced (XDR) или языка определения схемы XML.</span><span class="sxs-lookup"><span data-stu-id="ed789-104">To specify the allowed structure and content of an XML document, you can use a Document Type Definition (DTD), a Microsoft XML-Data Reduced (XDR) schema, or an XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="ed789-105">XSD-схемы являются предпочтительным способом для указания грамматики XML в [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed789-105">XSD schemas are the preferred way to specify XML grammars in the [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed789-106">В некоторых более ранних версиях Visual Studio **конструктор XML** — это конструктор для типизированных наборов данных и схемы XML.</span><span class="sxs-lookup"><span data-stu-id="ed789-106">In some earlier versions of Visual Studio, the **XML Designer** is the designer for typed datasets and XML schema.</span></span> <span data-ttu-id="ed789-107">**Конструктор XML** по-прежнему можно использовать для создания и редактирования файлов схемы XML.</span><span class="sxs-lookup"><span data-stu-id="ed789-107">The **XML Designer** can still be used to create and edit XML schema files.</span></span> <span data-ttu-id="ed789-108">Однако в [!INCLUDE[vs_current_long](../../csharp/misc/includes/vs_current_long_md.md)], конструктор для создания и редактирования типизированных наборов данных — **конструктора наборов данных**.</span><span class="sxs-lookup"><span data-stu-id="ed789-108">However, in [!INCLUDE[vs_current_long](../../csharp/misc/includes/vs_current_long_md.md)], the designer for creating and editing typed datasets is the **Dataset Designer**.</span></span> <span data-ttu-id="ed789-109">Дополнительные сведения см. в разделе [создания и редактирования типизированных наборов DataSet](https://docs.microsoft.com/visualstudio/data-tools/creating-and-editing-typed-datasets).</span><span class="sxs-lookup"><span data-stu-id="ed789-109">For more information, see [Creating and Editing Typed Datasets](https://docs.microsoft.com/visualstudio/data-tools/creating-and-editing-typed-datasets).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ed789-110">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="ed789-110">To correct this error</span></span>  
  
-   <span data-ttu-id="ed789-111">Убедитесь, что вы указали правильное имя файла.</span><span class="sxs-lookup"><span data-stu-id="ed789-111">Check that you are supplying the correct file name.</span></span>  
  
-   <span data-ttu-id="ed789-112">Убедитесь, что указанный файл содержит допустимый XML, загрузив XML-файл, который требуется проверить, в **конструктор XML**.</span><span class="sxs-lookup"><span data-stu-id="ed789-112">Check that the specified file contains valid XML by loading the XML file that you want to check into the **XML Designer**.</span></span> <span data-ttu-id="ed789-113">В меню **XML** выберите **Проверить XML**.</span><span class="sxs-lookup"><span data-stu-id="ed789-113">From the **XML** menu, click **Validate XML**.</span></span> <span data-ttu-id="ed789-114">Ошибки отображаются в **списке задач**.</span><span class="sxs-lookup"><span data-stu-id="ed789-114">Errors are displayed in the **Task List**.</span></span>  
  
-   <span data-ttu-id="ed789-115">Если XML-файл имеет связанную схему XML, удостоверьтесь, что элементы существуют в определенной структуре и что содержимое отдельных элементов соответствует объявленным типам данных, указанным в схеме.</span><span class="sxs-lookup"><span data-stu-id="ed789-115">If the XML file has an associated XML Schema, check that the elements appear in the defined structure and that the content of the individual elements conforms to the declared data types specified in the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed789-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ed789-116">See Also</span></span>  
 <span data-ttu-id="ed789-117"><xref:System.Xml></xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="ed789-117"><xref:System.Xml></span></span>   
<span data-ttu-id="ed789-118"> [Практическое руководство. Анализ путей к файлам](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)</span><span class="sxs-lookup"><span data-stu-id="ed789-118"> [How to: Parse File Paths](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)</span></span>
