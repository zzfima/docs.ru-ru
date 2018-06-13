---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: 4f731d146885265d9f956c182f1bebdba5db924b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486875"
---
# <a name="operationbehaviorattribute"></a><span data-ttu-id="95ee3-102">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="95ee3-102">OperationBehaviorAttribute</span></span>
<span data-ttu-id="95ee3-103">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="95ee3-103">OperationBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95ee3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95ee3-104">Syntax</span></span>  
  
```  
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="95ee3-105">Методы</span><span class="sxs-lookup"><span data-stu-id="95ee3-105">Methods</span></span>  
 <span data-ttu-id="95ee3-106">Класс OperationBehaviorAttribute не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="95ee3-106">The OperationBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="95ee3-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="95ee3-107">Properties</span></span>  
 <span data-ttu-id="95ee3-108">Класс OperationBehaviorAttribute имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="95ee3-108">The OperationBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="autodisposeparameters"></a><span data-ttu-id="95ee3-109">AutoDisposeParameters</span><span class="sxs-lookup"><span data-stu-id="95ee3-109">AutoDisposeParameters</span></span>  
 <span data-ttu-id="95ee3-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="95ee3-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="95ee3-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="95ee3-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="95ee3-112">Состояние функции автоматического удаления для параметров.</span><span class="sxs-lookup"><span data-stu-id="95ee3-112">The state of the auto-dispose feature for parameters.</span></span>  
  
### <a name="impersonation"></a><span data-ttu-id="95ee3-113">Олицетворение</span><span class="sxs-lookup"><span data-stu-id="95ee3-113">Impersonation</span></span>  
 <span data-ttu-id="95ee3-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="95ee3-114">Data type: string</span></span>  
  
 <span data-ttu-id="95ee3-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="95ee3-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="95ee3-116">Указывает уровень олицетворения вызывающей стороны, который поддерживает операция.</span><span class="sxs-lookup"><span data-stu-id="95ee3-116">Indicates the level of caller impersonation that the operation supports.</span></span>  
  
### <a name="releaseinstancemode"></a><span data-ttu-id="95ee3-117">ReleaseInstanceMode</span><span class="sxs-lookup"><span data-stu-id="95ee3-117">ReleaseInstanceMode</span></span>  
 <span data-ttu-id="95ee3-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="95ee3-118">Data type: string</span></span>  
  
 <span data-ttu-id="95ee3-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="95ee3-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="95ee3-120">Указывает, когда удалять объект в процессе вызова операции.</span><span class="sxs-lookup"><span data-stu-id="95ee3-120">Indicates when in the course of an operation invocation to recycle the object.</span></span>  
  
### <a name="transactionautocomplete"></a><span data-ttu-id="95ee3-121">TransactionAutoComplete</span><span class="sxs-lookup"><span data-stu-id="95ee3-121">TransactionAutoComplete</span></span>  
 <span data-ttu-id="95ee3-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="95ee3-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="95ee3-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="95ee3-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="95ee3-124">Указывает, следует ли автоматически фиксировать текущую транзакцию при отсутствии необработанных исключений.</span><span class="sxs-lookup"><span data-stu-id="95ee3-124">Indicates whether to automatically commit the current transaction if no unhandled exceptions occur.</span></span>  
  
### <a name="transactionscoperequired"></a><span data-ttu-id="95ee3-125">TransactionScopeRequired</span><span class="sxs-lookup"><span data-stu-id="95ee3-125">TransactionScopeRequired</span></span>  
 <span data-ttu-id="95ee3-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="95ee3-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="95ee3-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="95ee3-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="95ee3-128">Указывает, требует ли операция транзакции.</span><span class="sxs-lookup"><span data-stu-id="95ee3-128">Indicates whether the operation requires a transaction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95ee3-129">Требования</span><span class="sxs-lookup"><span data-stu-id="95ee3-129">Requirements</span></span>  
  
|<span data-ttu-id="95ee3-130">MOF</span><span class="sxs-lookup"><span data-stu-id="95ee3-130">MOF</span></span>|<span data-ttu-id="95ee3-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="95ee3-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="95ee3-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="95ee3-132">Namespace</span></span>|<span data-ttu-id="95ee3-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="95ee3-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="95ee3-134">См. также</span><span class="sxs-lookup"><span data-stu-id="95ee3-134">See Also</span></span>  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
