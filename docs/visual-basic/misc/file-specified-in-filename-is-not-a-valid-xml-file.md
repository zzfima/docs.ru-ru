---
title: Файл, указанный в FileName, не является допустимым XML-файлом
ms.date: 07/20/2015
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
ms.openlocfilehash: 5a54e5e7e7c75bb7d766b1bbda10f401fa8b99af
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65640829"
---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a><span data-ttu-id="48a90-102">Файл, указанный в FileName, не является допустимым XML-файлом</span><span class="sxs-lookup"><span data-stu-id="48a90-102">File specified in FileName is not a valid XML file</span></span>

<span data-ttu-id="48a90-103">Указанное имя файла не представляет допустимый XML-файл.</span><span class="sxs-lookup"><span data-stu-id="48a90-103">The file name that you supplied is not a valid XML file.</span></span> <span data-ttu-id="48a90-104">Чтобы задать допустимую структуру и содержимое XML-документа, можно использовать схему DTD, Microsoft XML-Data Reduced (XDR) или языка определения схемы XML.</span><span class="sxs-lookup"><span data-stu-id="48a90-104">To specify the allowed structure and content of an XML document, you can use a Document Type Definition (DTD), a Microsoft XML-Data Reduced (XDR) schema, or an XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="48a90-105">XSD-схемы являются предпочтительным способом указания грамматики XML в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="48a90-105">XSD schemas are the preferred way to specify XML grammars in the .NET Framework.</span></span>

> [!NOTE]
> <span data-ttu-id="48a90-106">В некоторых более ранних версиях Visual Studio **конструктор XML** — это конструктор для типизированных наборов данных и схемы XML.</span><span class="sxs-lookup"><span data-stu-id="48a90-106">In some earlier versions of Visual Studio, the **XML Designer** is the designer for typed datasets and XML schema.</span></span> <span data-ttu-id="48a90-107">**Конструктор XML** по-прежнему можно использовать для создания и редактирования файлов схемы XML.</span><span class="sxs-lookup"><span data-stu-id="48a90-107">The **XML Designer** can still be used to create and edit XML schema files.</span></span> <span data-ttu-id="48a90-108">Тем не менее, в Visual Studio 2012, конструктор для создания и редактирования типизированных наборов данных — **конструктор наборов данных**.</span><span class="sxs-lookup"><span data-stu-id="48a90-108">However, in Visual Studio 2012, the designer for creating and editing typed datasets is the **Dataset Designer**.</span></span> <span data-ttu-id="48a90-109">Дополнительные сведения см. в разделе [Создание и изменение типизированных наборов DataSet](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/314t4see(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="48a90-109">For more information, see [Creating and Editing Typed Datasets](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/314t4see(v=vs.120)).</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="48a90-110">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="48a90-110">To correct this error</span></span>

- <span data-ttu-id="48a90-111">Убедитесь, что вы указали правильное имя файла.</span><span class="sxs-lookup"><span data-stu-id="48a90-111">Check that you are supplying the correct file name.</span></span>

- <span data-ttu-id="48a90-112">Убедитесь, что указанный файл содержит допустимый XML, загрузив XML-файл, который требуется проверить, в **конструктор XML**.</span><span class="sxs-lookup"><span data-stu-id="48a90-112">Check that the specified file contains valid XML by loading the XML file that you want to check into the **XML Designer**.</span></span> <span data-ttu-id="48a90-113">В меню **XML** выберите **Проверить XML**.</span><span class="sxs-lookup"><span data-stu-id="48a90-113">From the **XML** menu, click **Validate XML**.</span></span> <span data-ttu-id="48a90-114">Ошибки отображаются в **списке задач**.</span><span class="sxs-lookup"><span data-stu-id="48a90-114">Errors are displayed in the **Task List**.</span></span>

- <span data-ttu-id="48a90-115">Если XML-файл имеет связанную схему XML, удостоверьтесь, что элементы существуют в определенной структуре и что содержимое отдельных элементов соответствует объявленным типам данных, указанным в схеме.</span><span class="sxs-lookup"><span data-stu-id="48a90-115">If the XML file has an associated XML Schema, check that the elements appear in the defined structure and that the content of the individual elements conforms to the declared data types specified in the schema.</span></span>

## <a name="see-also"></a><span data-ttu-id="48a90-116">См. также</span><span class="sxs-lookup"><span data-stu-id="48a90-116">See also</span></span>

- <xref:System.Xml>
- [<span data-ttu-id="48a90-117">Практическое руководство. Анализ путей к файлам</span><span class="sxs-lookup"><span data-stu-id="48a90-117">How to: Parse File Paths</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
