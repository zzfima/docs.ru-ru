---
title: ServiceTimeoutsBehavior
ms.date: 03/30/2017
ms.assetid: 4412525d-a3cc-4eae-b3e8-a50ce766d09d
ms.openlocfilehash: 58e872f2b15776d65bccdcc47c353ce566cd9d2f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956732"
---
# <a name="servicetimeoutsbehavior"></a><span data-ttu-id="7f4fe-102">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="7f4fe-102">ServiceTimeoutsBehavior</span></span>
<span data-ttu-id="7f4fe-103">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="7f4fe-103">ServiceTimeoutsBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f4fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f4fe-104">Syntax</span></span>  
  
```csharp
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7f4fe-105">Методы</span><span class="sxs-lookup"><span data-stu-id="7f4fe-105">Methods</span></span>  
 <span data-ttu-id="7f4fe-106">Класс ServiceTimeoutsBehavior не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="7f4fe-106">The ServiceTimeoutsBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7f4fe-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="7f4fe-107">Properties</span></span>  
 <span data-ttu-id="7f4fe-108">Класс ServiceTimeoutsBehavior имеет следующее свойство.</span><span class="sxs-lookup"><span data-stu-id="7f4fe-108">The ServiceTimeoutsBehavior class has the following property:</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="7f4fe-109">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="7f4fe-109">TransactionTimeout</span></span>  
 <span data-ttu-id="7f4fe-110">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="7f4fe-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="7f4fe-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="7f4fe-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7f4fe-112">Период времени, в течение которого транзакция должна быть завершена.</span><span class="sxs-lookup"><span data-stu-id="7f4fe-112">The period within which a transaction must complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f4fe-113">Требования</span><span class="sxs-lookup"><span data-stu-id="7f4fe-113">Requirements</span></span>  
  
|<span data-ttu-id="7f4fe-114">MOF</span><span class="sxs-lookup"><span data-stu-id="7f4fe-114">MOF</span></span>|<span data-ttu-id="7f4fe-115">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="7f4fe-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7f4fe-116">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="7f4fe-116">Namespace</span></span>|<span data-ttu-id="7f4fe-117">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="7f4fe-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7f4fe-118">См. также</span><span class="sxs-lookup"><span data-stu-id="7f4fe-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
