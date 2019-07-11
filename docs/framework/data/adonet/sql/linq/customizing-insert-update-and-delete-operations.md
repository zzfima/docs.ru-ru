---
title: Настройка операций вставки, обновления и удаления
ms.date: 03/30/2017
ms.assetid: 07eef055-8f6c-414d-850e-d323ff946cd0
ms.openlocfilehash: 114447fd45806e567b4fde8e9e74138c096bff07
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743567"
---
# <a name="customizing-insert-update-and-delete-operations"></a><span data-ttu-id="94783-102">Настройка операций вставки, обновления и удаления</span><span class="sxs-lookup"><span data-stu-id="94783-102">Customizing Insert, Update, and Delete Operations</span></span>
<span data-ttu-id="94783-103">По умолчанию [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает динамический SQL для выполнения операций чтения, обновления и удаления.</span><span class="sxs-lookup"><span data-stu-id="94783-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL to implement insert, read, update, and delete operations.</span></span> <span data-ttu-id="94783-104">Однако на практике обычно приходится настраивать приложение в соответствии с собственными бизнес-требованиями.</span><span class="sxs-lookup"><span data-stu-id="94783-104">In practice, however, you typically customize your application to suit your business needs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94783-105">Если вы используете Visual Studio, реляционный конструктор объектов можно использовать для настройки вставки, обновления и удаления действия.</span><span class="sxs-lookup"><span data-stu-id="94783-105">If you are using Visual Studio, you can use the Object Relational Designer to customize insert, update, and delete actions.</span></span>  
  
 <span data-ttu-id="94783-106">В данном разделе описываются методы, представляемые [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], для настройки операций вставки, чтения, обновления и удаления в приложении.</span><span class="sxs-lookup"><span data-stu-id="94783-106">This section of topics describes the techniques that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations in your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="94783-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="94783-107">In This Section</span></span>  
 [<span data-ttu-id="94783-108">Настройка операций. обзор</span><span class="sxs-lookup"><span data-stu-id="94783-108">Customizing Operations: Overview</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-overview.md)  
 <span data-ttu-id="94783-109">Содержит описание различных методов, представленных в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], для настройки операций вставки, чтения, обновления и удаления в приложении.</span><span class="sxs-lookup"><span data-stu-id="94783-109">Describes the various techniques [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="94783-110">Операции вставки, обновления и удаления</span><span class="sxs-lookup"><span data-stu-id="94783-110">Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/insert-update-and-delete-operations.md)  
 <span data-ttu-id="94783-111">Содержит описание заданных по умолчанию процессов [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] по управлению данными базы данных.</span><span class="sxs-lookup"><span data-stu-id="94783-111">Describes the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default processes for manipulating database data.</span></span>  
  
 [<span data-ttu-id="94783-112">Ответственность разработчика при переопределении поведения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="94783-112">Responsibilities of the Developer In Overriding Default Behavior</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)  
 <span data-ttu-id="94783-113">Содержит описание роли разработчиков в реализации требований, не примененных [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94783-113">Describes the role of the developer in implementing requirements not enforced by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="94783-114">Добавление бизнес-логики с использованием разделяемых методов</span><span class="sxs-lookup"><span data-stu-id="94783-114">Adding Business Logic By Using Partial Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)  
 <span data-ttu-id="94783-115">Содержит описание использования разделяемых методов для переопределения автоматически сгенерированных методов.</span><span class="sxs-lookup"><span data-stu-id="94783-115">Describes how to use partial methods to override autogenerated methods.</span></span>
