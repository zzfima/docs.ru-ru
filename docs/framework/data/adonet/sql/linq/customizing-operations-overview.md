---
title: 'Настройка операций: Обзор'
ms.date: 03/30/2017
ms.assetid: a3546296-1443-4b88-aa6e-d41011041ba7
ms.openlocfilehash: 48116887471709c60c9666f68c7ebdd0e6d128a1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247517"
---
# <a name="customizing-operations-overview"></a><span data-ttu-id="8d14e-102">Настройка операций: Обзор</span><span class="sxs-lookup"><span data-stu-id="8d14e-102">Customizing Operations: Overview</span></span>
<span data-ttu-id="8d14e-103">По умолчанию [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает динамический код SQL для операций вставки, обновления и удаления на основе сопоставления.</span><span class="sxs-lookup"><span data-stu-id="8d14e-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL for insert, update, and delete operations based on mapping.</span></span> <span data-ttu-id="8d14e-104">Однако на практике часто приходится добавлять собственную бизнес-логику для обеспечения безопасности, выполнения проверок и т. д.</span><span class="sxs-lookup"><span data-stu-id="8d14e-104">However, in practice you typically want to add your own business logic to provide for security, validation, and so forth.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="8d14e-105">Ниже приведены методы настройки этих операций.</span><span class="sxs-lookup"><span data-stu-id="8d14e-105">techniques for customizing these operations include the following.</span></span>  
  
## <a name="loading-options"></a><span data-ttu-id="8d14e-106">Возможности загрузки</span><span class="sxs-lookup"><span data-stu-id="8d14e-106">Loading Options</span></span>  
 <span data-ttu-id="8d14e-107">В запросах можно определять, какой объем данных, связанных с основными целевыми объектами, должен извлекаться при подключении к базе данных.</span><span class="sxs-lookup"><span data-stu-id="8d14e-107">In your queries, you can control how much data related to your main target is retrieved when you connect to the database.</span></span> <span data-ttu-id="8d14e-108">Эта функциональная возможность реализуется, в первую очередь, посредством использования параметров <xref:System.Data.Linq.DataLoadOptions>.</span><span class="sxs-lookup"><span data-stu-id="8d14e-108">This functionality is implemented largely by using <xref:System.Data.Linq.DataLoadOptions>.</span></span> <span data-ttu-id="8d14e-109">Дополнительные сведения см. в разделе [Отложенная и немедленная загрузка](deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="8d14e-109">For more information, see [Deferred versus Immediate Loading](deferred-versus-immediate-loading.md).</span></span>  
  
## <a name="partial-methods"></a><span data-ttu-id="8d14e-110">Разделяемые методы</span><span class="sxs-lookup"><span data-stu-id="8d14e-110">Partial Methods</span></span>  
 <span data-ttu-id="8d14e-111">При использовании сопоставления по умолчанию технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] предоставляет разделяемые методы, которые можно использовать для реализации пользовательской бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="8d14e-111">In its default mapping, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides partial methods to help you implement your business logic.</span></span> <span data-ttu-id="8d14e-112">Дополнительные сведения см. в разделе [Добавление бизнес-логики с помощью разделяемых методов](adding-business-logic-by-using-partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="8d14e-112">For more information, see [Adding Business Logic By Using Partial Methods](adding-business-logic-by-using-partial-methods.md).</span></span>  
  
## <a name="stored-procedures-and-user-defined-functions"></a><span data-ttu-id="8d14e-113">Хранимые процедуры и пользовательские функции</span><span class="sxs-lookup"><span data-stu-id="8d14e-113">Stored Procedures and User-Defined Functions</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="8d14e-114">поддерживает использование хранимых процедур и определяемых пользователем функций.</span><span class="sxs-lookup"><span data-stu-id="8d14e-114">supports the use of stored procedures and user-defined functions.</span></span> <span data-ttu-id="8d14e-115">Хранимые процедуры часто используются для настройки операций.</span><span class="sxs-lookup"><span data-stu-id="8d14e-115">Stored procedures are frequently used to customize operations.</span></span> <span data-ttu-id="8d14e-116">Дополнительные сведения см. в разделе [Хранимые процедуры](stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="8d14e-116">For more information, see [Stored Procedures](stored-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d14e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="8d14e-117">See also</span></span>

- [<span data-ttu-id="8d14e-118">Настройка операций вставки, обновления и удаления</span><span class="sxs-lookup"><span data-stu-id="8d14e-118">Customizing Insert, Update, and Delete Operations</span></span>](customizing-insert-update-and-delete-operations.md)
