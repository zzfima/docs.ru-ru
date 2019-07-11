---
title: Создание модели объектов
ms.date: 03/30/2017
ms.assetid: 27afce86-9b1d-45fb-8e0b-636bf671a236
ms.openlocfilehash: 0f1a0d035f2b11f33a9899ededd876155d45de3c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743585"
---
# <a name="creating-the-object-model"></a><span data-ttu-id="da3c8-102">Создание модели объектов</span><span class="sxs-lookup"><span data-stu-id="da3c8-102">Creating the Object Model</span></span>
<span data-ttu-id="da3c8-103">Объектную модель можно создать из существующей базы данных и использовать ее в заданном по умолчанию состоянии.</span><span class="sxs-lookup"><span data-stu-id="da3c8-103">You can create your object model from an existing database and use the model in its default state.</span></span> <span data-ttu-id="da3c8-104">Кроме того, можно настроить ряд аспектов модели и ее поведение.</span><span class="sxs-lookup"><span data-stu-id="da3c8-104">You can also customize many aspects of the model and its behavior.</span></span>  
  
 <span data-ttu-id="da3c8-105">Если вы используете Visual Studio, реляционный конструктор объектов можно использовать для создания объектной модели.</span><span class="sxs-lookup"><span data-stu-id="da3c8-105">If you are using Visual Studio, you can use the Object Relational Designer to create your object model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="da3c8-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="da3c8-106">In This Section</span></span>  
 [<span data-ttu-id="da3c8-107">Практическое руководство. Создание модели объектов на языке Visual Basic или C#</span><span class="sxs-lookup"><span data-stu-id="da3c8-107">How to: Generate the Object Model in Visual Basic or C#</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)  
 <span data-ttu-id="da3c8-108">Описано, как применять средство командной строки SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="da3c8-108">Describes how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="da3c8-109">Также содержит ссылку на реляционном конструкторе объектов для пользователей Visual Studio</span><span class="sxs-lookup"><span data-stu-id="da3c8-109">Also provides a link to the Object Relational Designer for Visual Studio users</span></span>  
  
 [<span data-ttu-id="da3c8-110">Практическое руководство. Создание модели объектов в виде внешнего файла</span><span class="sxs-lookup"><span data-stu-id="da3c8-110">How to: Generate the Object Model as an External File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-as-an-external-file.md)  
 <span data-ttu-id="da3c8-111">Содержит описание способов создания внешнего файла сопоставлений вместо использования сопоставления на основе атрибутов.</span><span class="sxs-lookup"><span data-stu-id="da3c8-111">Describes how to generate an external mapping file instead of using attribute-based mapping.</span></span>  
  
 [<span data-ttu-id="da3c8-112">Практическое руководство. Создать настраиваемый код путем изменения файла DBML</span><span class="sxs-lookup"><span data-stu-id="da3c8-112">How to: Generate Customized Code by Modifying a DBML File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-customized-code-by-modifying-a-dbml-file.md)  
 <span data-ttu-id="da3c8-113">Содержит описание способов создания Visual Basic или C# код из файла метаданных DBML.</span><span class="sxs-lookup"><span data-stu-id="da3c8-113">Describes how to generate Visual Basic or C# code from a DBML metadata file.</span></span>  
  
 [<span data-ttu-id="da3c8-114">Практическое руководство. Проверить DBML-файлы и внешние файлы сопоставлений</span><span class="sxs-lookup"><span data-stu-id="da3c8-114">How to: Validate DBML and External Mapping Files</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-validate-dbml-and-external-mapping-files.md)  
 <span data-ttu-id="da3c8-115">Содержит описание способов проверки измененных файлов сопоставлений (дополнительная возможность).</span><span class="sxs-lookup"><span data-stu-id="da3c8-115">Describes how to validate mapping files that you have modified (advanced).</span></span>  
  
 [<span data-ttu-id="da3c8-116">Практическое руководство. Обеспечение сериализуемости сущностей</span><span class="sxs-lookup"><span data-stu-id="da3c8-116">How to: Make Entities Serializable</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-make-entities-serializable.md)  
 <span data-ttu-id="da3c8-117">Содержит описание способов добавления соответствующих атрибутов для обеспечения возможности сериализации сущностей.</span><span class="sxs-lookup"><span data-stu-id="da3c8-117">Describes how to add appropriate attributes to make entities serializable.</span></span>  
  
 [<span data-ttu-id="da3c8-118">Практическое руководство. Настройка классов сущностей с помощью редактора кода</span><span class="sxs-lookup"><span data-stu-id="da3c8-118">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)  
 <span data-ttu-id="da3c8-119">Содержит описание способов использования редактора кода для написания собственного кода сопоставлений или изменения автоматически созданного кода.</span><span class="sxs-lookup"><span data-stu-id="da3c8-119">Describes how to use the code editor to write your own mapping code, or customize code that has been autogenerated.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="da3c8-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="da3c8-120">Related Sections</span></span>  
 [<span data-ttu-id="da3c8-121">Модель объектов LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="da3c8-121">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 <span data-ttu-id="da3c8-122">Предоставляет сведения о [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] объектной модели.</span><span class="sxs-lookup"><span data-stu-id="da3c8-122">Provides details about the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="da3c8-123">Стандартная последовательность действий при использовании LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="da3c8-123">Typical Steps for Using LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md)  
 <span data-ttu-id="da3c8-124">Содержит описание стандартных действий по реализации приложения [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da3c8-124">Explains the typical steps that you follow to implement a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] application.</span></span>
