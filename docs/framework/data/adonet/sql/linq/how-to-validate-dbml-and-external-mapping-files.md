---
title: Практическое руководство. Как проверять DBML-файлы и внешние файлы сопоставлений
ms.date: 03/30/2017
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
ms.openlocfilehash: 83a26f22495c849aa00143ca36b63fa147120c28
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59310243"
---
# <a name="how-to-validate-dbml-and-external-mapping-files"></a><span data-ttu-id="c802b-102">Практическое руководство. Как проверять DBML-файлы и внешние файлы сопоставлений</span><span class="sxs-lookup"><span data-stu-id="c802b-102">How to: Validate DBML and External Mapping Files</span></span>
<span data-ttu-id="c802b-103">После внесения изменений во внешние файлы сопоставлений и DBML-файлы их необходимо проверить на соответствие определениям схемы.</span><span class="sxs-lookup"><span data-stu-id="c802b-103">External mapping files and .dbml files that you modify must be validated against their respective schema definitions.</span></span> <span data-ttu-id="c802b-104">В этом разделе предоставляет пользователям Visual Studio, сделав для реализации процесса проверки.</span><span class="sxs-lookup"><span data-stu-id="c802b-104">This topic provides Visual Studio users with the steps to implement the validation process.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
### <a name="to-validate-a-dbml-or-xml-file"></a><span data-ttu-id="c802b-105">Проверка DBML-файла или XML-файла</span><span class="sxs-lookup"><span data-stu-id="c802b-105">To validate a .dbml or XML file</span></span>  
  
1. <span data-ttu-id="c802b-106">В Visual Studio **файл** последовательно выберите пункты **откройте**, а затем нажмите кнопку **файл**.</span><span class="sxs-lookup"><span data-stu-id="c802b-106">On the Visual Studio **File** menu, point to **Open**, and then click **File**.</span></span>  
  
2. <span data-ttu-id="c802b-107">В **открыть файл** диалогового окна выберите DBML-файл или файл сопоставления XML, который требуется проверить.</span><span class="sxs-lookup"><span data-stu-id="c802b-107">In the **Open File** dialog box, click the .dbml or XML mapping file that you want to validate.</span></span>  
  
     <span data-ttu-id="c802b-108">Файл откроется в **редактор XML**.</span><span class="sxs-lookup"><span data-stu-id="c802b-108">The file opens in the **XML Editor**.</span></span>  
  
3. <span data-ttu-id="c802b-109">Щелкните правой кнопкой мыши в окне и нажмите кнопку **свойства**.</span><span class="sxs-lookup"><span data-stu-id="c802b-109">Right-click the window, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="c802b-110">В **свойства** окно, нажмите кнопку с многоточием возле **схемы** свойство.</span><span class="sxs-lookup"><span data-stu-id="c802b-110">In the **Properties** window, click the ellipsis for the **Schemas** property.</span></span>  
  
     <span data-ttu-id="c802b-111">**XML-схем** откроется диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="c802b-111">The **XML Schemas** dialog box opens.</span></span>  
  
5. <span data-ttu-id="c802b-112">Отметьте определение схемы, соответствующее выполняемой задаче.</span><span class="sxs-lookup"><span data-stu-id="c802b-112">Note the appropriate schema definition for your purpose.</span></span>  
  
    -   <span data-ttu-id="c802b-113">Для проверки DBML-файла используется определение схемы DbmlSchema.xsd.</span><span class="sxs-lookup"><span data-stu-id="c802b-113">DbmlSchema.xsd is the schema definition for validating a .dbml file.</span></span> <span data-ttu-id="c802b-114">Дополнительные сведения см. в разделе [создание кода в LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c802b-114">For more information, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
    -   <span data-ttu-id="c802b-115">Для проверки внешнего XML-файла сопоставлений используется определение схемы LinqToSqlMapping.xsd.</span><span class="sxs-lookup"><span data-stu-id="c802b-115">LinqToSqlMapping.xsd is the schema definition for validating an external XML mapping file.</span></span> <span data-ttu-id="c802b-116">Дополнительные сведения см. в разделе [внешнего сопоставления](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="c802b-116">For more information, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
6. <span data-ttu-id="c802b-117">В **используйте** столбец нужной строки определения схемы, щелкните, чтобы открыть окно раскрывающегося списка и нажмите кнопку **использовать эту схему**.</span><span class="sxs-lookup"><span data-stu-id="c802b-117">In the **Use** column of the desired schema definition row, click to open the drop-down box, and then click **Use this schema**.</span></span>  
  
     <span data-ttu-id="c802b-118">Устанавливается связь между файлом определения схемы и файлом DBML или XML.</span><span class="sxs-lookup"><span data-stu-id="c802b-118">The schema definition file is now associated with your DBML or XML mapping file.</span></span>  
  
     <span data-ttu-id="c802b-119">Убедитесь, что не выбраны никакие другие определения схемы.</span><span class="sxs-lookup"><span data-stu-id="c802b-119">Make sure no other schema definitions are selected.</span></span>  
  
7. <span data-ttu-id="c802b-120">На **представление** меню, щелкните **список ошибок**.</span><span class="sxs-lookup"><span data-stu-id="c802b-120">On the **View** menu, click **Error List**.</span></span>  
  
     <span data-ttu-id="c802b-121">Проверьте, не было ли создано ошибок, предупреждений или сообщений.</span><span class="sxs-lookup"><span data-stu-id="c802b-121">Determine whether errors, warnings, or messages have been generated.</span></span> <span data-ttu-id="c802b-122">Если ошибки, предупреждения или сообщения отсутствуют, XML-файл соответствует определению схемы.</span><span class="sxs-lookup"><span data-stu-id="c802b-122">If not, the XML file is valid against the schema definition.</span></span>  
  
## <a name="alternate-method-for-supplying-schema-definition"></a><span data-ttu-id="c802b-123">Альтернативный метод получения определения схемы</span><span class="sxs-lookup"><span data-stu-id="c802b-123">Alternate Method for Supplying Schema Definition</span></span>  
 <span data-ttu-id="c802b-124">Если по некоторым причинам соответствующий XSD-файл в файл не **XML-схем** диалоговом окне можно загрузить XSD-файл из раздела справки.</span><span class="sxs-lookup"><span data-stu-id="c802b-124">If for some reason the appropriate .xsd file does not appear in the **XML Schemas** dialog box, you can download the .xsd file from a Help topic.</span></span> <span data-ttu-id="c802b-125">Следующие шаги помогут вам сохранить загруженный файл в формате Юникод, требуется по XML-редакторе Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c802b-125">The following steps help you save the downloaded file in the Unicode format required by the Visual Studio XML Editor.</span></span>  
  
#### <a name="to-copy-a-schema-definition-file-from-a-help-topic"></a><span data-ttu-id="c802b-126">Копирование файла определения схемы из раздела справки</span><span class="sxs-lookup"><span data-stu-id="c802b-126">To copy a schema definition file from a Help topic</span></span>  
  
1. <span data-ttu-id="c802b-127">Найдите раздел справки, который содержит определение схемы. Инструкции по выбору определения схемы см. ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="c802b-127">Locate the Help topic that contains the schema definition as described earlier in this topic.</span></span>  
  
    -   <span data-ttu-id="c802b-128">DBML-файлы, см. в разделе [создание кода в LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c802b-128">For .dbml files, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
    -   <span data-ttu-id="c802b-129">Файлы внешнего сопоставления см. в разделе [внешнего сопоставления](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="c802b-129">For external mapping files, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
2. <span data-ttu-id="c802b-130">Нажмите кнопку **Копировать код** для копирования в файл кода в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="c802b-130">Click **Copy Code** to copy the code file to the Clipboard.</span></span>  
  
3. <span data-ttu-id="c802b-131">Откройте текстовый редактор Блокнот и создайте новый файл.</span><span class="sxs-lookup"><span data-stu-id="c802b-131">Start Notepad to create a new file.</span></span>  
  
4. <span data-ttu-id="c802b-132">Вставьте код из буфера обмена в файл Блокнота.</span><span class="sxs-lookup"><span data-stu-id="c802b-132">Paste the code from the clipboard into Notepad file.</span></span>  
  
5. <span data-ttu-id="c802b-133">Блокнота **файл** меню, щелкните **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="c802b-133">On the Notepad **File** menu, click **Save As**.</span></span>  
  
6. <span data-ttu-id="c802b-134">В **кодировка** выберите **Юникода**.</span><span class="sxs-lookup"><span data-stu-id="c802b-134">In the **Encoding** box, select **Unicode**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c802b-135">Это действие гарантирует, что в начало текстового файла будет добавлена отметка порядка байтов Юникод-16 (`FFFE`).</span><span class="sxs-lookup"><span data-stu-id="c802b-135">This selection guarantees that the Unicode-16 byte-order marker (`FFFE`) is prepended to the text file.</span></span>  
  
7. <span data-ttu-id="c802b-136">В **имя файла** окне Создать имя файла с расширением XSD.</span><span class="sxs-lookup"><span data-stu-id="c802b-136">In the **File name** box, create a file name with an .xsd extension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c802b-137">См. также</span><span class="sxs-lookup"><span data-stu-id="c802b-137">See also</span></span>

- [<span data-ttu-id="c802b-138">Ссылки</span><span class="sxs-lookup"><span data-stu-id="c802b-138">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
