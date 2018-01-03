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
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 37f96338868183e8bf0397d9c0d09719fa3f7049
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="creating-the-object-model"></a><span data-ttu-id="31b85-102">Создание модели объектов</span><span class="sxs-lookup"><span data-stu-id="31b85-102">Creating the Object Model</span></span>
<span data-ttu-id="31b85-103">Объектную модель можно создать из существующей базы данных и использовать ее в заданном по умолчанию состоянии.</span><span class="sxs-lookup"><span data-stu-id="31b85-103">You can create your object model from an existing database and use the model in its default state.</span></span> <span data-ttu-id="31b85-104">Кроме того, можно настроить ряд аспектов модели и ее поведение.</span><span class="sxs-lookup"><span data-stu-id="31b85-104">You can also customize many aspects of the model and its behavior.</span></span>  
  
 <span data-ttu-id="31b85-105">Если вы используете [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], можно использовать [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для создания объектной модели.</span><span class="sxs-lookup"><span data-stu-id="31b85-105">If you are using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create your object model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="31b85-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="31b85-106">In This Section</span></span>  
 [<span data-ttu-id="31b85-107">Практическое руководство. Создание модели объектов в Visual Basic или C#</span><span class="sxs-lookup"><span data-stu-id="31b85-107">How to: Generate the Object Model in Visual Basic or C#</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)  
 <span data-ttu-id="31b85-108">Описано, как применять средство командной строки SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="31b85-108">Describes how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="31b85-109">Приведена также ссылка на среду [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для пользователей среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31b85-109">Also provides a link to the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] for [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] users</span></span>  
  
 [<span data-ttu-id="31b85-110">Практическое руководство. Создание модели объекта в виде внешнего файла</span><span class="sxs-lookup"><span data-stu-id="31b85-110">How to: Generate the Object Model as an External File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-as-an-external-file.md)  
 <span data-ttu-id="31b85-111">Содержит описание способов создания внешнего файла сопоставлений вместо использования сопоставления на основе атрибутов.</span><span class="sxs-lookup"><span data-stu-id="31b85-111">Describes how to generate an external mapping file instead of using attribute-based mapping.</span></span>  
  
 [<span data-ttu-id="31b85-112">Практическое руководство. Создание настраиваемого кода за счет изменения файла DBML</span><span class="sxs-lookup"><span data-stu-id="31b85-112">How to: Generate Customized Code by Modifying a DBML File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-customized-code-by-modifying-a-dbml-file.md)  
 <span data-ttu-id="31b85-113">Содержит описание способов создания кода [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] или C# из файла метаданных DBML.</span><span class="sxs-lookup"><span data-stu-id="31b85-113">Describes how to generate [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] or C# code from a DBML metadata file.</span></span>  
  
 [<span data-ttu-id="31b85-114">Практическое руководство. Проверка внешних файлов сопоставления и DBML-файлов</span><span class="sxs-lookup"><span data-stu-id="31b85-114">How to: Validate DBML and External Mapping Files</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-validate-dbml-and-external-mapping-files.md)  
 <span data-ttu-id="31b85-115">Содержит описание способов проверки измененных файлов сопоставлений (дополнительная возможность).</span><span class="sxs-lookup"><span data-stu-id="31b85-115">Describes how to validate mapping files that you have modified (advanced).</span></span>  
  
 [<span data-ttu-id="31b85-116">Практическое руководство. Обеспечение сериализуемости сущностей</span><span class="sxs-lookup"><span data-stu-id="31b85-116">How to: Make Entities Serializable</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-make-entities-serializable.md)  
 <span data-ttu-id="31b85-117">Содержит описание способов добавления соответствующих атрибутов для обеспечения возможности сериализации сущностей.</span><span class="sxs-lookup"><span data-stu-id="31b85-117">Describes how to add appropriate attributes to make entities serializable.</span></span>  
  
 [<span data-ttu-id="31b85-118">Практическое руководство. Настройка классов сущностей с использованием редактора кода</span><span class="sxs-lookup"><span data-stu-id="31b85-118">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)  
 <span data-ttu-id="31b85-119">Содержит описание способов использования редактора кода для написания собственного кода сопоставлений или изменения автоматически созданного кода.</span><span class="sxs-lookup"><span data-stu-id="31b85-119">Describes how to use the code editor to write your own mapping code, or customize code that has been autogenerated.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="31b85-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="31b85-120">Related Sections</span></span>  
 [<span data-ttu-id="31b85-121">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="31b85-121">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 <span data-ttu-id="31b85-122">Предоставляет подробные сведения о [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] объектной модели.</span><span class="sxs-lookup"><span data-stu-id="31b85-122">Provides details about the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="31b85-123">Стандартная последовательность действий при использовании LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="31b85-123">Typical Steps for Using LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md)  
 <span data-ttu-id="31b85-124">Содержит описание стандартных действий по реализации приложения [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31b85-124">Explains the typical steps that you follow to implement a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] application.</span></span>
