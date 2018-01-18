---
title: "Практическое руководство. Проверка внешних файлов сопоставления и DBML-файлов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 7724586c33c19654c3657a5a4604a3c74f2c8756
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-validate-dbml-and-external-mapping-files"></a><span data-ttu-id="0444c-102">Практическое руководство. Проверка внешних файлов сопоставления и DBML-файлов</span><span class="sxs-lookup"><span data-stu-id="0444c-102">How to: Validate DBML and External Mapping Files</span></span>
<span data-ttu-id="0444c-103">После внесения изменений во внешние файлы сопоставлений и DBML-файлы их необходимо проверить на соответствие определениям схемы.</span><span class="sxs-lookup"><span data-stu-id="0444c-103">External mapping files and .dbml files that you modify must be validated against their respective schema definitions.</span></span> <span data-ttu-id="0444c-104">Этот раздел предоставляет пользователям [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] шаги по реализации процесса проверки.</span><span class="sxs-lookup"><span data-stu-id="0444c-104">This topic provides [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] users with the steps to implement the validation process.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
### <a name="to-validate-a-dbml-or-xml-file"></a><span data-ttu-id="0444c-105">Проверка DBML-файла или XML-файла</span><span class="sxs-lookup"><span data-stu-id="0444c-105">To validate a .dbml or XML file</span></span>  
  
1.  <span data-ttu-id="0444c-106">В Visual Studio **файл** последовательно выберите пункты **откройте**, а затем нажмите кнопку **файл**.</span><span class="sxs-lookup"><span data-stu-id="0444c-106">On the Visual Studio **File** menu, point to **Open**, and then click **File**.</span></span>  
  
2.  <span data-ttu-id="0444c-107">В **открыть файл** диалогового окна выберите DBML-файл или XML-файл сопоставления, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="0444c-107">In the **Open File** dialog box, click the .dbml or XML mapping file that you want to validate.</span></span>  
  
     <span data-ttu-id="0444c-108">Файл откроется в **редактора XML**.</span><span class="sxs-lookup"><span data-stu-id="0444c-108">The file opens in the **XML Editor**.</span></span>  
  
3.  <span data-ttu-id="0444c-109">Щелкните правой кнопкой мыши окно и нажмите кнопку **свойства**.</span><span class="sxs-lookup"><span data-stu-id="0444c-109">Right-click the window, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="0444c-110">В **свойства** окно, нажмите кнопку с многоточием для **схемы** свойство.</span><span class="sxs-lookup"><span data-stu-id="0444c-110">In the **Properties** window, click the ellipsis for the **Schemas** property.</span></span>  
  
     <span data-ttu-id="0444c-111">**XML-схем** откроется диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="0444c-111">The **XML Schemas** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="0444c-112">Отметьте определение схемы, соответствующее выполняемой задаче.</span><span class="sxs-lookup"><span data-stu-id="0444c-112">Note the appropriate schema definition for your purpose.</span></span>  
  
    -   <span data-ttu-id="0444c-113">Для проверки DBML-файла используется определение схемы DbmlSchema.xsd.</span><span class="sxs-lookup"><span data-stu-id="0444c-113">DbmlSchema.xsd is the schema definition for validating a .dbml file.</span></span> <span data-ttu-id="0444c-114">Дополнительные сведения см. в разделе [создание кода в LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="0444c-114">For more information, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
    -   <span data-ttu-id="0444c-115">Для проверки внешнего XML-файла сопоставлений используется определение схемы LinqToSqlMapping.xsd.</span><span class="sxs-lookup"><span data-stu-id="0444c-115">LinqToSqlMapping.xsd is the schema definition for validating an external XML mapping file.</span></span> <span data-ttu-id="0444c-116">Дополнительные сведения см. в разделе [внешнего сопоставления](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="0444c-116">For more information, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
6.  <span data-ttu-id="0444c-117">В **используйте** столбец нужной строки определения схемы, щелкните, чтобы открыть поле раскрывающегося списка и нажмите кнопку **использовать эту схему**.</span><span class="sxs-lookup"><span data-stu-id="0444c-117">In the **Use** column of the desired schema definition row, click to open the drop-down box, and then click **Use this schema**.</span></span>  
  
     <span data-ttu-id="0444c-118">Устанавливается связь между файлом определения схемы и файлом DBML или XML.</span><span class="sxs-lookup"><span data-stu-id="0444c-118">The schema definition file is now associated with your DBML or XML mapping file.</span></span>  
  
     <span data-ttu-id="0444c-119">Убедитесь, что не выбраны никакие другие определения схемы.</span><span class="sxs-lookup"><span data-stu-id="0444c-119">Make sure no other schema definitions are selected.</span></span>  
  
7.  <span data-ttu-id="0444c-120">На **представление** меню, нажмите кнопку **список ошибок**.</span><span class="sxs-lookup"><span data-stu-id="0444c-120">On the **View** menu, click **Error List**.</span></span>  
  
     <span data-ttu-id="0444c-121">Проверьте, не было ли создано ошибок, предупреждений или сообщений.</span><span class="sxs-lookup"><span data-stu-id="0444c-121">Determine whether errors, warnings, or messages have been generated.</span></span> <span data-ttu-id="0444c-122">Если ошибки, предупреждения или сообщения отсутствуют, XML-файл соответствует определению схемы.</span><span class="sxs-lookup"><span data-stu-id="0444c-122">If not, the XML file is valid against the schema definition.</span></span>  
  
## <a name="alternate-method-for-supplying-schema-definition"></a><span data-ttu-id="0444c-123">Альтернативный метод получения определения схемы</span><span class="sxs-lookup"><span data-stu-id="0444c-123">Alternate Method for Supplying Schema Definition</span></span>  
 <span data-ttu-id="0444c-124">Если по некоторым причинам соответствующий XSD-файл не отображается в **XML-схем** диалоговое окно, можно загрузить XSD-файл из раздела справки.</span><span class="sxs-lookup"><span data-stu-id="0444c-124">If for some reason the appropriate .xsd file does not appear in the **XML Schemas** dialog box, you can download the .xsd file from a Help topic.</span></span> <span data-ttu-id="0444c-125">С помощью описанных ниже действий можно сохранить загруженный файл в формате Юникод, который требуется для редактора XML среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0444c-125">The following steps help you save the downloaded file in the Unicode format required by the [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] XML Editor.</span></span>  
  
#### <a name="to-copy-a-schema-definition-file-from-a-help-topic"></a><span data-ttu-id="0444c-126">Копирование файла определения схемы из раздела справки</span><span class="sxs-lookup"><span data-stu-id="0444c-126">To copy a schema definition file from a Help topic</span></span>  
  
1.  <span data-ttu-id="0444c-127">Найдите раздел справки, который содержит определение схемы. Инструкции по выбору определения схемы см. ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="0444c-127">Locate the Help topic that contains the schema definition as described earlier in this topic.</span></span>  
  
    -   <span data-ttu-id="0444c-128">DBML-файлы в разделе [создание кода в LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="0444c-128">For .dbml files, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
    -   <span data-ttu-id="0444c-129">Внешние файлы сопоставлений, в разделе [внешнего сопоставления](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="0444c-129">For external mapping files, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
2.  <span data-ttu-id="0444c-130">Нажмите кнопку **Копировать код** для копирования в файл кода в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="0444c-130">Click **Copy Code** to copy the code file to the Clipboard.</span></span>  
  
3.  <span data-ttu-id="0444c-131">Откройте текстовый редактор Блокнот и создайте новый файл.</span><span class="sxs-lookup"><span data-stu-id="0444c-131">Start Notepad to create a new file.</span></span>  
  
4.  <span data-ttu-id="0444c-132">Вставьте код из буфера обмена в файл Блокнота.</span><span class="sxs-lookup"><span data-stu-id="0444c-132">Paste the code from the clipboard into Notepad file.</span></span>  
  
5.  <span data-ttu-id="0444c-133">Блокнота **файл** меню, нажмите кнопку **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="0444c-133">On the Notepad **File** menu, click **Save As**.</span></span>  
  
6.  <span data-ttu-id="0444c-134">В **кодировка** выберите **Юникода**.</span><span class="sxs-lookup"><span data-stu-id="0444c-134">In the **Encoding** box, select **Unicode**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="0444c-135">Это действие гарантирует, что в начало текстового файла будет добавлена отметка порядка байтов Юникод-16 (`FFFE`).</span><span class="sxs-lookup"><span data-stu-id="0444c-135">This selection guarantees that the Unicode-16 byte-order marker (`FFFE`) is prepended to the text file.</span></span>  
  
7.  <span data-ttu-id="0444c-136">В **имя файла** Создайте имя файла с расширением XSD.</span><span class="sxs-lookup"><span data-stu-id="0444c-136">In the **File name** box, create a file name with an .xsd extension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0444c-137">См. также</span><span class="sxs-lookup"><span data-stu-id="0444c-137">See Also</span></span>  
 [<span data-ttu-id="0444c-138">Ссылки</span><span class="sxs-lookup"><span data-stu-id="0444c-138">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
