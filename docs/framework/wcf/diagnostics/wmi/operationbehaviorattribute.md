---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: d0bf59e6064748a045f761777a2f8f3e88f1cb5a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504331"
---
# <a name="operationbehaviorattribute"></a><span data-ttu-id="9ee1f-102">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="9ee1f-102">OperationBehaviorAttribute</span></span>
<span data-ttu-id="9ee1f-103">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="9ee1f-103">OperationBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ee1f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ee1f-104">Syntax</span></span>  
  
```csharp
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9ee1f-105">Методы</span><span class="sxs-lookup"><span data-stu-id="9ee1f-105">Methods</span></span>  
 <span data-ttu-id="9ee1f-106">Класс OperationBehaviorAttribute не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="9ee1f-106">The OperationBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9ee1f-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="9ee1f-107">Properties</span></span>  
 <span data-ttu-id="9ee1f-108">Класс OperationBehaviorAttribute имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="9ee1f-108">The OperationBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="autodisposeparameters"></a><span data-ttu-id="9ee1f-109">AutoDisposeParameters</span><span class="sxs-lookup"><span data-stu-id="9ee1f-109">AutoDisposeParameters</span></span>  
 <span data-ttu-id="9ee1f-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="9ee1f-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="9ee1f-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="9ee1f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ee1f-112">Состояние возможности автоматического удаления для параметров.</span><span class="sxs-lookup"><span data-stu-id="9ee1f-112">The state of the auto-dispose feature for parameters.</span></span>  
  
### <a name="impersonation"></a><span data-ttu-id="9ee1f-113">Олицетворение</span><span class="sxs-lookup"><span data-stu-id="9ee1f-113">Impersonation</span></span>  
 <span data-ttu-id="9ee1f-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="9ee1f-114">Data type: string</span></span>  
  
 <span data-ttu-id="9ee1f-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="9ee1f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ee1f-116">Указывает уровень олицетворения вызывающей стороны, который поддерживает операция.</span><span class="sxs-lookup"><span data-stu-id="9ee1f-116">Indicates the level of caller impersonation that the operation supports.</span></span>  
  
### <a name="releaseinstancemode"></a><span data-ttu-id="9ee1f-117">ReleaseInstanceMode</span><span class="sxs-lookup"><span data-stu-id="9ee1f-117">ReleaseInstanceMode</span></span>  
 <span data-ttu-id="9ee1f-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="9ee1f-118">Data type: string</span></span>  
  
 <span data-ttu-id="9ee1f-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="9ee1f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ee1f-120">Указывает, когда удалять объект в процессе вызова операции.</span><span class="sxs-lookup"><span data-stu-id="9ee1f-120">Indicates when in the course of an operation invocation to recycle the object.</span></span>  
  
### <a name="transactionautocomplete"></a><span data-ttu-id="9ee1f-121">TransactionAutoComplete</span><span class="sxs-lookup"><span data-stu-id="9ee1f-121">TransactionAutoComplete</span></span>  
 <span data-ttu-id="9ee1f-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="9ee1f-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="9ee1f-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="9ee1f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ee1f-124">Указывает, следует ли автоматически фиксировать текущую транзакцию при отсутствии необработанных исключений.</span><span class="sxs-lookup"><span data-stu-id="9ee1f-124">Indicates whether to automatically commit the current transaction if no unhandled exceptions occur.</span></span>  
  
### <a name="transactionscoperequired"></a><span data-ttu-id="9ee1f-125">TransactionScopeRequired</span><span class="sxs-lookup"><span data-stu-id="9ee1f-125">TransactionScopeRequired</span></span>  
 <span data-ttu-id="9ee1f-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="9ee1f-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="9ee1f-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="9ee1f-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ee1f-128">Указывает, требует ли операция транзакции.</span><span class="sxs-lookup"><span data-stu-id="9ee1f-128">Indicates whether the operation requires a transaction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ee1f-129">Требования</span><span class="sxs-lookup"><span data-stu-id="9ee1f-129">Requirements</span></span>  
  
|<span data-ttu-id="9ee1f-130">MOF</span><span class="sxs-lookup"><span data-stu-id="9ee1f-130">MOF</span></span>|<span data-ttu-id="9ee1f-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9ee1f-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9ee1f-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="9ee1f-132">Namespace</span></span>|<span data-ttu-id="9ee1f-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="9ee1f-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ee1f-134">См. также</span><span class="sxs-lookup"><span data-stu-id="9ee1f-134">See also</span></span>
- <xref:System.ServiceModel.OperationBehaviorAttribute>
