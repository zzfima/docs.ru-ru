---
title: "Класс Operation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 54566bc452baa2e02cef7d8d13d29fcd5864c95c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="operation-class"></a><span data-ttu-id="2aa34-102">Класс Operation</span><span class="sxs-lookup"><span data-stu-id="2aa34-102">Operation class</span></span>
<span data-ttu-id="2aa34-103">Операция</span><span class="sxs-lookup"><span data-stu-id="2aa34-103">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2aa34-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2aa34-104">Syntax</span></span>  
  
```  
class Operation  
{  
  string Action;  
  boolean AsyncPattern;  
  Behavior Behaviors[];  
  boolean IsCallback;  
  boolean IsInitiating;  
  boolean IsOneWay;  
  boolean IsTerminating;  
  string MethodSignature;  
  string Name;  
  string ParameterTypes[];  
  string ReplyAction;  
  string ReturnType;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2aa34-105">Методы</span><span class="sxs-lookup"><span data-stu-id="2aa34-105">Methods</span></span>  
 <span data-ttu-id="2aa34-106">Класс Operation не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="2aa34-106">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2aa34-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="2aa34-107">Properties</span></span>  
 <span data-ttu-id="2aa34-108">Класс Operation имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="2aa34-108">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="2aa34-109">Действие</span><span class="sxs-lookup"><span data-stu-id="2aa34-109">Action</span></span>  
 <span data-ttu-id="2aa34-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="2aa34-110">Data type: string</span></span>  
  
 <span data-ttu-id="2aa34-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="2aa34-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2aa34-112">Действие WS-Addressing сообщения запроса.</span><span class="sxs-lookup"><span data-stu-id="2aa34-112">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="2aa34-113">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="2aa34-113">AsyncPattern</span></span>  
 <span data-ttu-id="2aa34-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="2aa34-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="2aa34-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="2aa34-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2aa34-116">Указывает, что операция реализуется асинхронно с помощью `Begin`[открыть/закрыть угловые скобки] и `End`пары методов [открыть/закрыть угловые скобки] в контракте службы.</span><span class="sxs-lookup"><span data-stu-id="2aa34-116">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="2aa34-117">поведения</span><span class="sxs-lookup"><span data-stu-id="2aa34-117">Behaviors</span></span>  
 <span data-ttu-id="2aa34-118">Тип данных: массив Behavior</span><span class="sxs-lookup"><span data-stu-id="2aa34-118">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="2aa34-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="2aa34-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2aa34-120">Поведения, связанные с этой операцией.</span><span class="sxs-lookup"><span data-stu-id="2aa34-120">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="2aa34-121">IsCallback</span><span class="sxs-lookup"><span data-stu-id="2aa34-121">IsCallback</span></span>  
 <span data-ttu-id="2aa34-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="2aa34-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="2aa34-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="2aa34-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2aa34-124">Истинно, если операция является операцией обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="2aa34-124">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="2aa34-125">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="2aa34-125">IsInitiating</span></span>  
 <span data-ttu-id="2aa34-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="2aa34-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="2aa34-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="2aa34-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2aa34-128">Показывает, реализует ли метод операцию, которая может инициировать сеанс на сервере.</span><span class="sxs-lookup"><span data-stu-id="2aa34-128">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="2aa34-129">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="2aa34-129">IsOneWay</span></span>  
 <span data-ttu-id="2aa34-130">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="2aa34-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="2aa34-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="2aa34-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2aa34-132">Показывает, возвращает ли операция ответное сообщение.</span><span class="sxs-lookup"><span data-stu-id="2aa34-132">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="2aa34-133">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="2aa34-133">IsTerminating</span></span>  
 <span data-ttu-id="2aa34-134">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="2aa34-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="2aa34-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="2aa34-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2aa34-136">Показывает, возвращает ли операция ответное сообщение.</span><span class="sxs-lookup"><span data-stu-id="2aa34-136">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="2aa34-137">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="2aa34-137">MethodSignature</span></span>  
 <span data-ttu-id="2aa34-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="2aa34-138">Data type: string</span></span>  
  
 <span data-ttu-id="2aa34-139">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="2aa34-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2aa34-140">Подпись метода операции.</span><span class="sxs-lookup"><span data-stu-id="2aa34-140">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="2aa34-141">name</span><span class="sxs-lookup"><span data-stu-id="2aa34-141">Name</span></span>  
 <span data-ttu-id="2aa34-142">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="2aa34-142">Data type: string</span></span>  
  
 <span data-ttu-id="2aa34-143">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="2aa34-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2aa34-144">Имя операции.</span><span class="sxs-lookup"><span data-stu-id="2aa34-144">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="2aa34-145">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="2aa34-145">ParameterTypes</span></span>  
 <span data-ttu-id="2aa34-146">Тип данных: массив строк</span><span class="sxs-lookup"><span data-stu-id="2aa34-146">Data type: string array</span></span>  
  
 <span data-ttu-id="2aa34-147">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="2aa34-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2aa34-148">Типы параметров операции.</span><span class="sxs-lookup"><span data-stu-id="2aa34-148">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="2aa34-149">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="2aa34-149">ReplyAction</span></span>  
 <span data-ttu-id="2aa34-150">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="2aa34-150">Data type: string</span></span>  
  
 <span data-ttu-id="2aa34-151">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="2aa34-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2aa34-152">Значение действия SOAP для ответного сообщения операции.</span><span class="sxs-lookup"><span data-stu-id="2aa34-152">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="2aa34-153">ReturnType</span><span class="sxs-lookup"><span data-stu-id="2aa34-153">ReturnType</span></span>  
 <span data-ttu-id="2aa34-154">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="2aa34-154">Data type: string</span></span>  
  
 <span data-ttu-id="2aa34-155">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="2aa34-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2aa34-156">Тип возвращаемого значения операции.</span><span class="sxs-lookup"><span data-stu-id="2aa34-156">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2aa34-157">Требования</span><span class="sxs-lookup"><span data-stu-id="2aa34-157">Requirements</span></span>  
  
|<span data-ttu-id="2aa34-158">MOF</span><span class="sxs-lookup"><span data-stu-id="2aa34-158">MOF</span></span>|<span data-ttu-id="2aa34-159">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="2aa34-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2aa34-160">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="2aa34-160">Namespace</span></span>|<span data-ttu-id="2aa34-161">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="2aa34-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2aa34-162">См. также</span><span class="sxs-lookup"><span data-stu-id="2aa34-162">See Also</span></span>  
 <xref:System.ServiceModel.Description.OperationDescription>
