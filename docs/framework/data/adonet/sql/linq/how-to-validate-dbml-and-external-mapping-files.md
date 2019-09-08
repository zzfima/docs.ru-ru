---
title: Практическое руководство. Как проверять DBML-файлы и внешние файлы сопоставлений
ms.date: 03/30/2017
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
ms.openlocfilehash: b5901705ac7c0692025ff1f4a4b78f976d62176d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793040"
---
# <a name="how-to-validate-dbml-and-external-mapping-files"></a><span data-ttu-id="a14c8-102">Практическое руководство. Как проверять DBML-файлы и внешние файлы сопоставлений</span><span class="sxs-lookup"><span data-stu-id="a14c8-102">How to: Validate DBML and External Mapping Files</span></span>

<span data-ttu-id="a14c8-103">После внесения изменений во внешние файлы сопоставлений и DBML-файлы их необходимо проверить на соответствие определениям схемы.</span><span class="sxs-lookup"><span data-stu-id="a14c8-103">External mapping files and .dbml files that you modify must be validated against their respective schema definitions.</span></span> <span data-ttu-id="a14c8-104">Этот раздел предоставляет пользователям Visual Studio инструкции по реализации процесса проверки.</span><span class="sxs-lookup"><span data-stu-id="a14c8-104">This topic provides Visual Studio users with the steps to implement the validation process.</span></span>

[!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]

### <a name="to-validate-a-dbml-or-xml-file"></a><span data-ttu-id="a14c8-105">Проверка DBML-файла или XML-файла</span><span class="sxs-lookup"><span data-stu-id="a14c8-105">To validate a .dbml or XML file</span></span>

1. <span data-ttu-id="a14c8-106">В меню **файл** Visual Studio наведите указатель мыши на пункт **Открыть**и выберите пункт **файл**.</span><span class="sxs-lookup"><span data-stu-id="a14c8-106">On the Visual Studio **File** menu, point to **Open**, and then click **File**.</span></span>

2. <span data-ttu-id="a14c8-107">В диалоговом окне **Открытие файла** выберите файл сопоставления. DBML или XML, который требуется проверить.</span><span class="sxs-lookup"><span data-stu-id="a14c8-107">In the **Open File** dialog box, click the .dbml or XML mapping file that you want to validate.</span></span>

    <span data-ttu-id="a14c8-108">Файл откроется в **редакторе XML**.</span><span class="sxs-lookup"><span data-stu-id="a14c8-108">The file opens in the **XML Editor**.</span></span>

3. <span data-ttu-id="a14c8-109">Щелкните правой кнопкой мыши окно и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="a14c8-109">Right-click the window, and then click **Properties**.</span></span>

4. <span data-ttu-id="a14c8-110">В окне **Свойства** нажмите кнопку с многоточием для свойства **схемы** .</span><span class="sxs-lookup"><span data-stu-id="a14c8-110">In the **Properties** window, click the ellipsis for the **Schemas** property.</span></span>

    <span data-ttu-id="a14c8-111">Откроется диалоговое окно **схемы XML** .</span><span class="sxs-lookup"><span data-stu-id="a14c8-111">The **XML Schemas** dialog box opens.</span></span>

5. <span data-ttu-id="a14c8-112">Отметьте определение схемы, соответствующее выполняемой задаче.</span><span class="sxs-lookup"><span data-stu-id="a14c8-112">Note the appropriate schema definition for your purpose.</span></span>

    - <span data-ttu-id="a14c8-113">Для проверки DBML-файла используется определение схемы DbmlSchema.xsd.</span><span class="sxs-lookup"><span data-stu-id="a14c8-113">DbmlSchema.xsd is the schema definition for validating a .dbml file.</span></span> <span data-ttu-id="a14c8-114">Дополнительные сведения см. [в разделе Создание кода в LINQ to SQL](code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a14c8-114">For more information, see [Code Generation in LINQ to SQL](code-generation-in-linq-to-sql.md).</span></span>

    - <span data-ttu-id="a14c8-115">Для проверки внешнего XML-файла сопоставлений используется определение схемы LinqToSqlMapping.xsd.</span><span class="sxs-lookup"><span data-stu-id="a14c8-115">LinqToSqlMapping.xsd is the schema definition for validating an external XML mapping file.</span></span> <span data-ttu-id="a14c8-116">Дополнительные сведения см. в разделе [внешнее сопоставление](external-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="a14c8-116">For more information, see [External Mapping](external-mapping.md).</span></span>

6. <span data-ttu-id="a14c8-117">В столбце **использовать** в строке определения требуемой схемы щелкните, чтобы открыть раскрывающийся список, и выберите **использовать эту схему**.</span><span class="sxs-lookup"><span data-stu-id="a14c8-117">In the **Use** column of the desired schema definition row, click to open the drop-down box, and then click **Use this schema**.</span></span>

    <span data-ttu-id="a14c8-118">Устанавливается связь между файлом определения схемы и файлом DBML или XML.</span><span class="sxs-lookup"><span data-stu-id="a14c8-118">The schema definition file is now associated with your DBML or XML mapping file.</span></span>

    <span data-ttu-id="a14c8-119">Убедитесь, что не выбраны никакие другие определения схемы.</span><span class="sxs-lookup"><span data-stu-id="a14c8-119">Make sure no other schema definitions are selected.</span></span>

7. <span data-ttu-id="a14c8-120">В меню **вид** выберите пункт **Список ошибок**.</span><span class="sxs-lookup"><span data-stu-id="a14c8-120">On the **View** menu, click **Error List**.</span></span>

    <span data-ttu-id="a14c8-121">Проверьте, не было ли создано ошибок, предупреждений или сообщений.</span><span class="sxs-lookup"><span data-stu-id="a14c8-121">Determine whether errors, warnings, or messages have been generated.</span></span> <span data-ttu-id="a14c8-122">Если ошибки, предупреждения или сообщения отсутствуют, XML-файл соответствует определению схемы.</span><span class="sxs-lookup"><span data-stu-id="a14c8-122">If not, the XML file is valid against the schema definition.</span></span>

## <a name="alternate-method-for-supplying-schema-definition"></a><span data-ttu-id="a14c8-123">Альтернативный метод получения определения схемы</span><span class="sxs-lookup"><span data-stu-id="a14c8-123">Alternate Method for Supplying Schema Definition</span></span>

<span data-ttu-id="a14c8-124">Если по какой-либо причине соответствующий XSD-файл не отображается в диалоговом окне **схемы XML** , можно скачать XSD-файл из раздела справки.</span><span class="sxs-lookup"><span data-stu-id="a14c8-124">If for some reason the appropriate .xsd file does not appear in the **XML Schemas** dialog box, you can download the .xsd file from a Help topic.</span></span> <span data-ttu-id="a14c8-125">Следующие шаги помогут сохранить скачанный файл в формате Юникод, требуемом редактором Visual Studio XML.</span><span class="sxs-lookup"><span data-stu-id="a14c8-125">The following steps help you save the downloaded file in the Unicode format required by the Visual Studio XML Editor.</span></span>

#### <a name="to-copy-a-schema-definition-file-from-a-help-topic"></a><span data-ttu-id="a14c8-126">Копирование файла определения схемы из раздела справки</span><span class="sxs-lookup"><span data-stu-id="a14c8-126">To copy a schema definition file from a Help topic</span></span>

1. <span data-ttu-id="a14c8-127">Найдите раздел справки, который содержит определение схемы. Инструкции по выбору определения схемы см. ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="a14c8-127">Locate the Help topic that contains the schema definition as described earlier in this topic.</span></span>

    - <span data-ttu-id="a14c8-128">Сведения о файлах. dbml см. [в разделе Создание кода в LINQ to SQL](code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a14c8-128">For .dbml files, see [Code Generation in LINQ to SQL](code-generation-in-linq-to-sql.md).</span></span>

    - <span data-ttu-id="a14c8-129">Сведения о внешних файлах сопоставлений см. в разделе [внешнее сопоставление](external-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="a14c8-129">For external mapping files, see [External Mapping](external-mapping.md).</span></span>

2. <span data-ttu-id="a14c8-130">Щелкните **Копировать код** , чтобы скопировать файл кода в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="a14c8-130">Click **Copy Code** to copy the code file to the Clipboard.</span></span>

3. <span data-ttu-id="a14c8-131">Откройте текстовый редактор Блокнот и создайте новый файл.</span><span class="sxs-lookup"><span data-stu-id="a14c8-131">Start Notepad to create a new file.</span></span>

4. <span data-ttu-id="a14c8-132">Вставьте код из буфера обмена в файл Блокнота.</span><span class="sxs-lookup"><span data-stu-id="a14c8-132">Paste the code from the clipboard into Notepad file.</span></span>

5. <span data-ttu-id="a14c8-133">В меню " **файл** " выберите команду " **Сохранить как**".</span><span class="sxs-lookup"><span data-stu-id="a14c8-133">On the Notepad **File** menu, click **Save As**.</span></span>

6. <span data-ttu-id="a14c8-134">В поле **Кодировка** выберите **Юникод**.</span><span class="sxs-lookup"><span data-stu-id="a14c8-134">In the **Encoding** box, select **Unicode**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a14c8-135">Это действие гарантирует, что в начало текстового файла будет добавлена отметка порядка байтов Юникод-16 (`FFFE`).</span><span class="sxs-lookup"><span data-stu-id="a14c8-135">This selection guarantees that the Unicode-16 byte-order marker (`FFFE`) is prepended to the text file.</span></span>

7. <span data-ttu-id="a14c8-136">В поле **имя файла** создайте имя файла с расширением XSD.</span><span class="sxs-lookup"><span data-stu-id="a14c8-136">In the **File name** box, create a file name with an .xsd extension.</span></span>

## <a name="see-also"></a><span data-ttu-id="a14c8-137">См. также</span><span class="sxs-lookup"><span data-stu-id="a14c8-137">See also</span></span>

- [<span data-ttu-id="a14c8-138">Ссылки</span><span class="sxs-lookup"><span data-stu-id="a14c8-138">Reference</span></span>](reference.md)
