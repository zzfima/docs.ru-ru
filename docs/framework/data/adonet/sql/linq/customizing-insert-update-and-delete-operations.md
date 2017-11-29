---
title: "Настройка операций вставки, обновления и удаления"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 07eef055-8f6c-414d-850e-d323ff946cd0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e48ac307087d5b90567c720d0c215ac0d52ccb6b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="customizing-insert-update-and-delete-operations"></a><span data-ttu-id="b7a01-102">Настройка операций вставки, обновления и удаления</span><span class="sxs-lookup"><span data-stu-id="b7a01-102">Customizing Insert, Update, and Delete Operations</span></span>
<span data-ttu-id="b7a01-103">По умолчанию [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает динамический SQL для выполнения операций чтения, обновления и удаления.</span><span class="sxs-lookup"><span data-stu-id="b7a01-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL to implement insert, read, update, and delete operations.</span></span> <span data-ttu-id="b7a01-104">Однако на практике обычно приходится настраивать приложение в соответствии с собственными бизнес-требованиями.</span><span class="sxs-lookup"><span data-stu-id="b7a01-104">In practice, however, you typically customize your application to suit your business needs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7a01-105">Если вы используете [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], то операции вставки, обновления и удаления можно настроить с помощью [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7a01-105">If you are using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to customize insert, update, and delete actions.</span></span>  
  
 <span data-ttu-id="b7a01-106">В данном разделе описываются методы, представляемые [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], для настройки операций вставки, чтения, обновления и удаления в приложении.</span><span class="sxs-lookup"><span data-stu-id="b7a01-106">This section of topics describes the techniques that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations in your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b7a01-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="b7a01-107">In This Section</span></span>  
 [<span data-ttu-id="b7a01-108">Настройка операций: Общие сведения</span><span class="sxs-lookup"><span data-stu-id="b7a01-108">Customizing Operations: Overview</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-overview.md)  
 <span data-ttu-id="b7a01-109">Содержит описание различных методов, представленных в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], для настройки операций вставки, чтения, обновления и удаления в приложении.</span><span class="sxs-lookup"><span data-stu-id="b7a01-109">Describes the various techniques [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="b7a01-110">Операций вставки, обновления и удаления</span><span class="sxs-lookup"><span data-stu-id="b7a01-110">Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/insert-update-and-delete-operations.md)  
 <span data-ttu-id="b7a01-111">Содержит описание заданных по умолчанию процессов [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] по управлению данными базы данных.</span><span class="sxs-lookup"><span data-stu-id="b7a01-111">Describes the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default processes for manipulating database data.</span></span>  
  
 [<span data-ttu-id="b7a01-112">Обязанности разработчика при переопределении поведения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b7a01-112">Responsibilities of the Developer In Overriding Default Behavior</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)  
 <span data-ttu-id="b7a01-113">Содержит описание роли разработчиков в реализации требований, не примененных [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7a01-113">Describes the role of the developer in implementing requirements not enforced by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="b7a01-114">Добавление бизнес-логики с помощью разделяемых методов</span><span class="sxs-lookup"><span data-stu-id="b7a01-114">Adding Business Logic By Using Partial Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)  
 <span data-ttu-id="b7a01-115">Содержит описание использования разделяемых методов для переопределения автоматически сгенерированных методов.</span><span class="sxs-lookup"><span data-stu-id="b7a01-115">Describes how to use partial methods to override autogenerated methods.</span></span>
