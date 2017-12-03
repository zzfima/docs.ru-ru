---
title: OperationBehaviorAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: da0bc2ac9a4283ec9b23a1d4767f664de071ef47
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="operationbehaviorattribute"></a><span data-ttu-id="224a1-102">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="224a1-102">OperationBehaviorAttribute</span></span>
<span data-ttu-id="224a1-103">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="224a1-103">OperationBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="224a1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="224a1-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="224a1-105">Методы</span><span class="sxs-lookup"><span data-stu-id="224a1-105">Methods</span></span>  
 <span data-ttu-id="224a1-106">Класс OperationBehaviorAttribute не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="224a1-106">The OperationBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="224a1-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="224a1-107">Properties</span></span>  
 <span data-ttu-id="224a1-108">Класс OperationBehaviorAttribute имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="224a1-108">The OperationBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="autodisposeparameters"></a><span data-ttu-id="224a1-109">AutoDisposeParameters</span><span class="sxs-lookup"><span data-stu-id="224a1-109">AutoDisposeParameters</span></span>  
 <span data-ttu-id="224a1-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="224a1-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="224a1-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="224a1-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="224a1-112">Состояние функции автоматического удаления для параметров.</span><span class="sxs-lookup"><span data-stu-id="224a1-112">The state of the auto-dispose feature for parameters.</span></span>  
  
### <a name="impersonation"></a><span data-ttu-id="224a1-113">Олицетворение</span><span class="sxs-lookup"><span data-stu-id="224a1-113">Impersonation</span></span>  
 <span data-ttu-id="224a1-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="224a1-114">Data type: string</span></span>  
  
 <span data-ttu-id="224a1-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="224a1-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="224a1-116">Указывает уровень олицетворения вызывающей стороны, который поддерживает операция.</span><span class="sxs-lookup"><span data-stu-id="224a1-116">Indicates the level of caller impersonation that the operation supports.</span></span>  
  
### <a name="releaseinstancemode"></a><span data-ttu-id="224a1-117">ReleaseInstanceMode</span><span class="sxs-lookup"><span data-stu-id="224a1-117">ReleaseInstanceMode</span></span>  
 <span data-ttu-id="224a1-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="224a1-118">Data type: string</span></span>  
  
 <span data-ttu-id="224a1-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="224a1-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="224a1-120">Указывает, когда удалять объект в процессе вызова операции.</span><span class="sxs-lookup"><span data-stu-id="224a1-120">Indicates when in the course of an operation invocation to recycle the object.</span></span>  
  
### <a name="transactionautocomplete"></a><span data-ttu-id="224a1-121">TransactionAutoComplete</span><span class="sxs-lookup"><span data-stu-id="224a1-121">TransactionAutoComplete</span></span>  
 <span data-ttu-id="224a1-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="224a1-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="224a1-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="224a1-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="224a1-124">Указывает, следует ли автоматически фиксировать текущую транзакцию при отсутствии необработанных исключений.</span><span class="sxs-lookup"><span data-stu-id="224a1-124">Indicates whether to automatically commit the current transaction if no unhandled exceptions occur.</span></span>  
  
### <a name="transactionscoperequired"></a><span data-ttu-id="224a1-125">TransactionScopeRequired</span><span class="sxs-lookup"><span data-stu-id="224a1-125">TransactionScopeRequired</span></span>  
 <span data-ttu-id="224a1-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="224a1-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="224a1-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="224a1-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="224a1-128">Указывает, требует ли операция транзакции.</span><span class="sxs-lookup"><span data-stu-id="224a1-128">Indicates whether the operation requires a transaction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="224a1-129">Требования</span><span class="sxs-lookup"><span data-stu-id="224a1-129">Requirements</span></span>  
  
|<span data-ttu-id="224a1-130">MOF</span><span class="sxs-lookup"><span data-stu-id="224a1-130">MOF</span></span>|<span data-ttu-id="224a1-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="224a1-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="224a1-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="224a1-132">Namespace</span></span>|<span data-ttu-id="224a1-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="224a1-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="224a1-134">См. также</span><span class="sxs-lookup"><span data-stu-id="224a1-134">See Also</span></span>  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
