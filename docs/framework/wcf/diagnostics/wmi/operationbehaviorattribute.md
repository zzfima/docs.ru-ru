---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: 79601308c66abe43dd5a7f72bd2a05b9d2346c2b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975160"
---
# <a name="operationbehaviorattribute"></a><span data-ttu-id="4e903-102">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="4e903-102">OperationBehaviorAttribute</span></span>
<span data-ttu-id="4e903-103">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="4e903-103">OperationBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e903-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e903-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="4e903-105">Методы</span><span class="sxs-lookup"><span data-stu-id="4e903-105">Methods</span></span>  
 <span data-ttu-id="4e903-106">Класс OperationBehaviorAttribute не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="4e903-106">The OperationBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4e903-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="4e903-107">Properties</span></span>  
 <span data-ttu-id="4e903-108">Класс OperationBehaviorAttribute имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="4e903-108">The OperationBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="autodisposeparameters"></a><span data-ttu-id="4e903-109">AutoDisposeParameters</span><span class="sxs-lookup"><span data-stu-id="4e903-109">AutoDisposeParameters</span></span>  
 <span data-ttu-id="4e903-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="4e903-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="4e903-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="4e903-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e903-112">Состояние возможности автоматического удаления для параметров.</span><span class="sxs-lookup"><span data-stu-id="4e903-112">The state of the auto-dispose feature for parameters.</span></span>  
  
### <a name="impersonation"></a><span data-ttu-id="4e903-113">Олицетворение</span><span class="sxs-lookup"><span data-stu-id="4e903-113">Impersonation</span></span>  
 <span data-ttu-id="4e903-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="4e903-114">Data type: string</span></span>  
  
 <span data-ttu-id="4e903-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="4e903-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e903-116">Указывает уровень олицетворения вызывающей стороны, который поддерживает операция.</span><span class="sxs-lookup"><span data-stu-id="4e903-116">Indicates the level of caller impersonation that the operation supports.</span></span>  
  
### <a name="releaseinstancemode"></a><span data-ttu-id="4e903-117">ReleaseInstanceMode</span><span class="sxs-lookup"><span data-stu-id="4e903-117">ReleaseInstanceMode</span></span>  
 <span data-ttu-id="4e903-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="4e903-118">Data type: string</span></span>  
  
 <span data-ttu-id="4e903-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="4e903-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e903-120">Указывает, когда удалять объект в процессе вызова операции.</span><span class="sxs-lookup"><span data-stu-id="4e903-120">Indicates when in the course of an operation invocation to recycle the object.</span></span>  
  
### <a name="transactionautocomplete"></a><span data-ttu-id="4e903-121">TransactionAutoComplete</span><span class="sxs-lookup"><span data-stu-id="4e903-121">TransactionAutoComplete</span></span>  
 <span data-ttu-id="4e903-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="4e903-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="4e903-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="4e903-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e903-124">Указывает, следует ли автоматически фиксировать текущую транзакцию при отсутствии необработанных исключений.</span><span class="sxs-lookup"><span data-stu-id="4e903-124">Indicates whether to automatically commit the current transaction if no unhandled exceptions occur.</span></span>  
  
### <a name="transactionscoperequired"></a><span data-ttu-id="4e903-125">TransactionScopeRequired</span><span class="sxs-lookup"><span data-stu-id="4e903-125">TransactionScopeRequired</span></span>  
 <span data-ttu-id="4e903-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="4e903-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="4e903-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="4e903-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e903-128">Указывает, требует ли операция транзакции.</span><span class="sxs-lookup"><span data-stu-id="4e903-128">Indicates whether the operation requires a transaction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e903-129">Требования</span><span class="sxs-lookup"><span data-stu-id="4e903-129">Requirements</span></span>  
  
|<span data-ttu-id="4e903-130">MOF</span><span class="sxs-lookup"><span data-stu-id="4e903-130">MOF</span></span>|<span data-ttu-id="4e903-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4e903-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4e903-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="4e903-132">Namespace</span></span>|<span data-ttu-id="4e903-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="4e903-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4e903-134">См. также</span><span class="sxs-lookup"><span data-stu-id="4e903-134">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
