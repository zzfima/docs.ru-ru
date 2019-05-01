---
title: Настройка операций вставки, обновления и удаления
ms.date: 03/30/2017
ms.assetid: 07eef055-8f6c-414d-850e-d323ff946cd0
ms.openlocfilehash: b4578a030300872bf4e0bab30b8daf12544be0cf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032777"
---
# <a name="customizing-insert-update-and-delete-operations"></a><span data-ttu-id="945c4-102">Настройка операций вставки, обновления и удаления</span><span class="sxs-lookup"><span data-stu-id="945c4-102">Customizing Insert, Update, and Delete Operations</span></span>
<span data-ttu-id="945c4-103">По умолчанию [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает динамический SQL для выполнения операций чтения, обновления и удаления.</span><span class="sxs-lookup"><span data-stu-id="945c4-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL to implement insert, read, update, and delete operations.</span></span> <span data-ttu-id="945c4-104">Однако на практике обычно приходится настраивать приложение в соответствии с собственными бизнес-требованиями.</span><span class="sxs-lookup"><span data-stu-id="945c4-104">In practice, however, you typically customize your application to suit your business needs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="945c4-105">Если вы используете Visual Studio, можно использовать [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для настройки вставки, обновления и удаления действия.</span><span class="sxs-lookup"><span data-stu-id="945c4-105">If you are using Visual Studio, you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to customize insert, update, and delete actions.</span></span>  
  
 <span data-ttu-id="945c4-106">В данном разделе описываются методы, представляемые [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], для настройки операций вставки, чтения, обновления и удаления в приложении.</span><span class="sxs-lookup"><span data-stu-id="945c4-106">This section of topics describes the techniques that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations in your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="945c4-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="945c4-107">In This Section</span></span>  
 [<span data-ttu-id="945c4-108">Настройка операций. обзор</span><span class="sxs-lookup"><span data-stu-id="945c4-108">Customizing Operations: Overview</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-overview.md)  
 <span data-ttu-id="945c4-109">Содержит описание различных методов, представленных в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], для настройки операций вставки, чтения, обновления и удаления в приложении.</span><span class="sxs-lookup"><span data-stu-id="945c4-109">Describes the various techniques [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="945c4-110">Операции вставки, обновления и удаления</span><span class="sxs-lookup"><span data-stu-id="945c4-110">Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/insert-update-and-delete-operations.md)  
 <span data-ttu-id="945c4-111">Содержит описание заданных по умолчанию процессов [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] по управлению данными базы данных.</span><span class="sxs-lookup"><span data-stu-id="945c4-111">Describes the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default processes for manipulating database data.</span></span>  
  
 [<span data-ttu-id="945c4-112">Ответственность разработчика при переопределении поведения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="945c4-112">Responsibilities of the Developer In Overriding Default Behavior</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)  
 <span data-ttu-id="945c4-113">Содержит описание роли разработчиков в реализации требований, не примененных [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="945c4-113">Describes the role of the developer in implementing requirements not enforced by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="945c4-114">Добавление бизнес-логики с использованием разделяемых методов</span><span class="sxs-lookup"><span data-stu-id="945c4-114">Adding Business Logic By Using Partial Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)  
 <span data-ttu-id="945c4-115">Содержит описание использования разделяемых методов для переопределения автоматически сгенерированных методов.</span><span class="sxs-lookup"><span data-stu-id="945c4-115">Describes how to use partial methods to override autogenerated methods.</span></span>
