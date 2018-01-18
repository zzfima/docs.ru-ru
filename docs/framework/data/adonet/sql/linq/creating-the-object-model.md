---
title: "Создание модели объектов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27afce86-9b1d-45fb-8e0b-636bf671a236
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bb6f8683ce49c8115b6dce477d0e61369d7abeef
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="creating-the-object-model"></a><span data-ttu-id="6f062-102">Создание модели объектов</span><span class="sxs-lookup"><span data-stu-id="6f062-102">Creating the Object Model</span></span>
<span data-ttu-id="6f062-103">Объектную модель можно создать из существующей базы данных и использовать ее в заданном по умолчанию состоянии.</span><span class="sxs-lookup"><span data-stu-id="6f062-103">You can create your object model from an existing database and use the model in its default state.</span></span> <span data-ttu-id="6f062-104">Кроме того, можно настроить ряд аспектов модели и ее поведение.</span><span class="sxs-lookup"><span data-stu-id="6f062-104">You can also customize many aspects of the model and its behavior.</span></span>  
  
 <span data-ttu-id="6f062-105">Если вы используете [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], можно использовать [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для создания объектной модели.</span><span class="sxs-lookup"><span data-stu-id="6f062-105">If you are using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create your object model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6f062-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="6f062-106">In This Section</span></span>  
 [<span data-ttu-id="6f062-107">Практическое руководство. Создание модели объектов в Visual Basic или C#</span><span class="sxs-lookup"><span data-stu-id="6f062-107">How to: Generate the Object Model in Visual Basic or C#</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)  
 <span data-ttu-id="6f062-108">Описано, как применять средство командной строки SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="6f062-108">Describes how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="6f062-109">Приведена также ссылка на среду [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для пользователей среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f062-109">Also provides a link to the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] for [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] users</span></span>  
  
 [<span data-ttu-id="6f062-110">Практическое руководство. Создание модели объекта в виде внешнего файла</span><span class="sxs-lookup"><span data-stu-id="6f062-110">How to: Generate the Object Model as an External File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-as-an-external-file.md)  
 <span data-ttu-id="6f062-111">Содержит описание способов создания внешнего файла сопоставлений вместо использования сопоставления на основе атрибутов.</span><span class="sxs-lookup"><span data-stu-id="6f062-111">Describes how to generate an external mapping file instead of using attribute-based mapping.</span></span>  
  
 [<span data-ttu-id="6f062-112">Практическое руководство. Создание настраиваемого кода за счет изменения файла DBML</span><span class="sxs-lookup"><span data-stu-id="6f062-112">How to: Generate Customized Code by Modifying a DBML File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-customized-code-by-modifying-a-dbml-file.md)  
 <span data-ttu-id="6f062-113">Содержит описание способов создания кода [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] или C# из файла метаданных DBML.</span><span class="sxs-lookup"><span data-stu-id="6f062-113">Describes how to generate [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] or C# code from a DBML metadata file.</span></span>  
  
 [<span data-ttu-id="6f062-114">Практическое руководство. Проверка внешних файлов сопоставления и DBML-файлов</span><span class="sxs-lookup"><span data-stu-id="6f062-114">How to: Validate DBML and External Mapping Files</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-validate-dbml-and-external-mapping-files.md)  
 <span data-ttu-id="6f062-115">Содержит описание способов проверки измененных файлов сопоставлений (дополнительная возможность).</span><span class="sxs-lookup"><span data-stu-id="6f062-115">Describes how to validate mapping files that you have modified (advanced).</span></span>  
  
 [<span data-ttu-id="6f062-116">Практическое руководство. Обеспечение сериализуемости сущностей</span><span class="sxs-lookup"><span data-stu-id="6f062-116">How to: Make Entities Serializable</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-make-entities-serializable.md)  
 <span data-ttu-id="6f062-117">Содержит описание способов добавления соответствующих атрибутов для обеспечения возможности сериализации сущностей.</span><span class="sxs-lookup"><span data-stu-id="6f062-117">Describes how to add appropriate attributes to make entities serializable.</span></span>  
  
 [<span data-ttu-id="6f062-118">Практическое руководство. Настройка классов сущностей с использованием редактора кода</span><span class="sxs-lookup"><span data-stu-id="6f062-118">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)  
 <span data-ttu-id="6f062-119">Содержит описание способов использования редактора кода для написания собственного кода сопоставлений или изменения автоматически созданного кода.</span><span class="sxs-lookup"><span data-stu-id="6f062-119">Describes how to use the code editor to write your own mapping code, or customize code that has been autogenerated.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6f062-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="6f062-120">Related Sections</span></span>  
 [<span data-ttu-id="6f062-121">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="6f062-121">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 <span data-ttu-id="6f062-122">Предоставляет подробные сведения о [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] объектной модели.</span><span class="sxs-lookup"><span data-stu-id="6f062-122">Provides details about the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="6f062-123">Стандартная последовательность действий при использовании LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="6f062-123">Typical Steps for Using LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md)  
 <span data-ttu-id="6f062-124">Содержит описание стандартных действий по реализации приложения [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f062-124">Explains the typical steps that you follow to implement a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] application.</span></span>
