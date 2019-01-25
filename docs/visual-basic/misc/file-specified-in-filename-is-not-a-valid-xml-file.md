---
title: Файл, указанный в FileName, не является допустимым XML-файлом
ms.date: 07/20/2015
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
ms.openlocfilehash: ffa39653c20127bb6af5e85654fee940a191fe5b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603535"
---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a><span data-ttu-id="812fc-102">Файл, указанный в FileName, не является допустимым XML-файлом</span><span class="sxs-lookup"><span data-stu-id="812fc-102">File specified in FileName is not a valid XML file</span></span>
<span data-ttu-id="812fc-103">Указанное имя файла не представляет допустимый XML-файл.</span><span class="sxs-lookup"><span data-stu-id="812fc-103">The file name that you supplied is not a valid XML file.</span></span> <span data-ttu-id="812fc-104">Чтобы задать допустимую структуру и содержимое XML-документа, можно использовать схему DTD, Microsoft XML-Data Reduced (XDR) или языка определения схемы XML.</span><span class="sxs-lookup"><span data-stu-id="812fc-104">To specify the allowed structure and content of an XML document, you can use a Document Type Definition (DTD), a Microsoft XML-Data Reduced (XDR) schema, or an XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="812fc-105">Для указания грамматики XML в [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]предпочтительнее использовать схемы XSD.</span><span class="sxs-lookup"><span data-stu-id="812fc-105">XSD schemas are the preferred way to specify XML grammars in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>

> [!NOTE]
>  <span data-ttu-id="812fc-106">В некоторых более ранних версиях Visual Studio **конструктор XML** — это конструктор для типизированных наборов данных и схемы XML.</span><span class="sxs-lookup"><span data-stu-id="812fc-106">In some earlier versions of Visual Studio, the **XML Designer** is the designer for typed datasets and XML schema.</span></span> <span data-ttu-id="812fc-107">**Конструктор XML** по-прежнему можно использовать для создания и редактирования файлов схемы XML.</span><span class="sxs-lookup"><span data-stu-id="812fc-107">The **XML Designer** can still be used to create and edit XML schema files.</span></span> <span data-ttu-id="812fc-108">Тем не менее, в Visual Studio 2012, конструктор для создания и редактирования типизированных наборов данных — **конструктор наборов данных**.</span><span class="sxs-lookup"><span data-stu-id="812fc-108">However, in Visual Studio 2012, the designer for creating and editing typed datasets is the **Dataset Designer**.</span></span> <span data-ttu-id="812fc-109">Дополнительные сведения см. в разделе [Создание и изменение типизированных наборов DataSet](/visualstudio/data-tools/creating-and-editing-typed-datasets).</span><span class="sxs-lookup"><span data-stu-id="812fc-109">For more information, see [Creating and Editing Typed Datasets](/visualstudio/data-tools/creating-and-editing-typed-datasets).</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="812fc-110">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="812fc-110">To correct this error</span></span>

-   <span data-ttu-id="812fc-111">Убедитесь, что вы указали правильное имя файла.</span><span class="sxs-lookup"><span data-stu-id="812fc-111">Check that you are supplying the correct file name.</span></span>

-   <span data-ttu-id="812fc-112">Убедитесь, что указанный файл содержит допустимый XML, загрузив XML-файл, который требуется проверить, в **конструктор XML**.</span><span class="sxs-lookup"><span data-stu-id="812fc-112">Check that the specified file contains valid XML by loading the XML file that you want to check into the **XML Designer**.</span></span> <span data-ttu-id="812fc-113">В меню **XML** выберите **Проверить XML**.</span><span class="sxs-lookup"><span data-stu-id="812fc-113">From the **XML** menu, click **Validate XML**.</span></span> <span data-ttu-id="812fc-114">Ошибки отображаются в **списке задач**.</span><span class="sxs-lookup"><span data-stu-id="812fc-114">Errors are displayed in the **Task List**.</span></span>

-   <span data-ttu-id="812fc-115">Если XML-файл имеет связанную схему XML, удостоверьтесь, что элементы существуют в определенной структуре и что содержимое отдельных элементов соответствует объявленным типам данных, указанным в схеме.</span><span class="sxs-lookup"><span data-stu-id="812fc-115">If the XML file has an associated XML Schema, check that the elements appear in the defined structure and that the content of the individual elements conforms to the declared data types specified in the schema.</span></span>

## <a name="see-also"></a><span data-ttu-id="812fc-116">См. также</span><span class="sxs-lookup"><span data-stu-id="812fc-116">See also</span></span>

- <xref:System.Xml>
- [<span data-ttu-id="812fc-117">Практическое руководство. Анализ путей к файлам</span><span class="sxs-lookup"><span data-stu-id="812fc-117">How to: Parse File Paths</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)