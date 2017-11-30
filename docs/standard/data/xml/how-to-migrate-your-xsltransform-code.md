---
title: "Как осуществить перенос кода XslTransform"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 910beb2f-cfb3-4e8e-9936-f7e0c5f4064a
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f8a9e287e611e1cb1731c267702504637b23081b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-migrate-your-xsltransform-code"></a><span data-ttu-id="20343-102">Как осуществить перенос кода XslTransform</span><span class="sxs-lookup"><span data-stu-id="20343-102">How to: Migrate Your XslTransform Code</span></span>
<span data-ttu-id="20343-103">Новые классы XSLT разработаны так, чтобы быть похожими на существующие классы.</span><span class="sxs-lookup"><span data-stu-id="20343-103">The new XSLT classes have been designed to be very similar to the existing classes.</span></span> <span data-ttu-id="20343-104">Класс <xref:System.Xml.Xsl.XslCompiledTransform> заменяет класс <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="20343-104">The <xref:System.Xml.Xsl.XslCompiledTransform> class replaces the <xref:System.Xml.Xsl.XslTransform> class.</span></span> <span data-ttu-id="20343-105">Таблицы стилей компилируются с помощью метода <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="20343-105">Style sheets are compiled using the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method.</span></span> <span data-ttu-id="20343-106">Преобразования выполняются с помощью метода <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="20343-106">Transforms are executed using the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span> <span data-ttu-id="20343-107">В следующей процедуре показаны распространенные XSLT-задачи, а сравнивается код использования классов <xref:System.Xml.Xsl.XslTransform> и <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="20343-107">The following procedures show common XSLT tasks, and compare the code using the <xref:System.Xml.Xsl.XslTransform> class versus the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
### <a name="to-transform-a-file-and-output-to-a-uri"></a><span data-ttu-id="20343-108">Преобразование файла и вывод в URI</span><span class="sxs-lookup"><span data-stu-id="20343-108">To transform a file and output to a URI</span></span>  
  
-   <span data-ttu-id="20343-109">Код с использованием класса <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="20343-109">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#9](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#9)]
     [!code-vb[XML_Migration#9](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#9)]  
  
-   <span data-ttu-id="20343-110">Код с использованием класса <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="20343-110">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#10](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#10)]
     [!code-vb[XML_Migration#10](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#10)]  
  
### <a name="to-compile-a-style-sheet-and-use-a-resolver-with-default-credentials"></a><span data-ttu-id="20343-111">Компиляция таблицы стилей и использование арбитра с учетными данными по умолчанию</span><span class="sxs-lookup"><span data-stu-id="20343-111">To compile a style sheet and use a resolver with default credentials</span></span>  
  
-   <span data-ttu-id="20343-112">Код с использованием класса <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="20343-112">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#11](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#11)]
     [!code-vb[XML_Migration#11](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#11)]  
  
-   <span data-ttu-id="20343-113">Код с использованием класса <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="20343-113">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#12](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#12)]
     [!code-vb[XML_Migration#12](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#12)]  
  
### <a name="to-use-an-xslt-parameter"></a><span data-ttu-id="20343-114">Использование параметра XSLT</span><span class="sxs-lookup"><span data-stu-id="20343-114">To use an XSLT parameter</span></span>  
  
-   <span data-ttu-id="20343-115">Код с использованием класса <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="20343-115">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#13](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#13)]
     [!code-vb[XML_Migration#13](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#13)]  
  
-   <span data-ttu-id="20343-116">Код с использованием класса <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="20343-116">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#14](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#14)]
     [!code-vb[XML_Migration#14](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#14)]  
  
### <a name="to-enable-xslt-scripting"></a><span data-ttu-id="20343-117">Включение XSLT-скриптов</span><span class="sxs-lookup"><span data-stu-id="20343-117">To enable XSLT scripting</span></span>  
  
-   <span data-ttu-id="20343-118">Код с использованием класса <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="20343-118">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#15](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#15)]
     [!code-vb[XML_Migration#15](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#15)]  
  
-   <span data-ttu-id="20343-119">Код с использованием класса <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="20343-119">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#16](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#16)]
     [!code-vb[XML_Migration#16](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#16)]  
  
### <a name="to-load-the-results-into-a-dom-object"></a><span data-ttu-id="20343-120">Загрузка результатов в объект модели DOM</span><span class="sxs-lookup"><span data-stu-id="20343-120">To load the results into a DOM object</span></span>  
  
-   <span data-ttu-id="20343-121">Код с использованием класса <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="20343-121">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#19](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#19)]
     [!code-vb[XML_Migration#19](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#19)]  
  
-   <span data-ttu-id="20343-122">Код с использованием класса <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="20343-122">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="20343-123">Класс <xref:System.Xml.Xsl.XslCompiledTransform> не имеет метода, возвращающего результаты XSLT-преобразования в виде объекта <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="20343-123">The <xref:System.Xml.Xsl.XslCompiledTransform> class does not have a method that returns the XSLT transformation results as an <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="20343-124">Однако можно сохранить выходные данные в XML-файл и загрузить его в другой объект.</span><span class="sxs-lookup"><span data-stu-id="20343-124">However, you can output to an XML file and load the XML file into another object.</span></span>  
  
     [!code-csharp[XML_Migration#20](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#20)]
     [!code-vb[XML_Migration#20](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#20)]  
  
### <a name="to-stream-the-results-into-another-data-store"></a><span data-ttu-id="20343-125">Потоковый вывод данных в другое хранилище данных</span><span class="sxs-lookup"><span data-stu-id="20343-125">To stream the results into another data store</span></span>  
  
-   <span data-ttu-id="20343-126">Код с использованием класса <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="20343-126">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#17](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#17)]
     [!code-vb[XML_Migration#17](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#17)]  
  
-   <span data-ttu-id="20343-127">Код с использованием класса <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="20343-127">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#18](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#18)]
     [!code-vb[XML_Migration#18](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#18)]  
  
## <a name="see-also"></a><span data-ttu-id="20343-128">См. также</span><span class="sxs-lookup"><span data-stu-id="20343-128">See Also</span></span>  
 [<span data-ttu-id="20343-129">Миграция с класса XslTransform</span><span class="sxs-lookup"><span data-stu-id="20343-129">Migrating From the XslTransform Class</span></span>](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 [<span data-ttu-id="20343-130">Использование класса XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="20343-130">Using the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)
