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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 739f8309e7a01eeecf921b50fcde24417fbbc515
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="operation-class"></a><span data-ttu-id="f801e-102">Класс Operation</span><span class="sxs-lookup"><span data-stu-id="f801e-102">Operation class</span></span>
<span data-ttu-id="f801e-103">Операция</span><span class="sxs-lookup"><span data-stu-id="f801e-103">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f801e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f801e-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="f801e-105">Методы</span><span class="sxs-lookup"><span data-stu-id="f801e-105">Methods</span></span>  
 <span data-ttu-id="f801e-106">Класс Operation не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="f801e-106">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f801e-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="f801e-107">Properties</span></span>  
 <span data-ttu-id="f801e-108">Класс Operation имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="f801e-108">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="f801e-109">Действие</span><span class="sxs-lookup"><span data-stu-id="f801e-109">Action</span></span>  
 <span data-ttu-id="f801e-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f801e-110">Data type: string</span></span>  
  
 <span data-ttu-id="f801e-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f801e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f801e-112">Действие WS-Addressing сообщения запроса.</span><span class="sxs-lookup"><span data-stu-id="f801e-112">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="f801e-113">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="f801e-113">AsyncPattern</span></span>  
 <span data-ttu-id="f801e-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="f801e-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="f801e-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f801e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f801e-116">Указывает, что операция реализуется асинхронно с помощью `Begin`[открыть/закрыть угловые скобки] и `End`пары методов [открыть/закрыть угловые скобки] в контракте службы.</span><span class="sxs-lookup"><span data-stu-id="f801e-116">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="f801e-117">поведения</span><span class="sxs-lookup"><span data-stu-id="f801e-117">Behaviors</span></span>  
 <span data-ttu-id="f801e-118">Тип данных: массив Behavior</span><span class="sxs-lookup"><span data-stu-id="f801e-118">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="f801e-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f801e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f801e-120">Поведения, связанные с этой операцией.</span><span class="sxs-lookup"><span data-stu-id="f801e-120">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="f801e-121">IsCallback</span><span class="sxs-lookup"><span data-stu-id="f801e-121">IsCallback</span></span>  
 <span data-ttu-id="f801e-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="f801e-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="f801e-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f801e-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f801e-124">Истинно, если операция является операцией обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="f801e-124">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="f801e-125">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="f801e-125">IsInitiating</span></span>  
 <span data-ttu-id="f801e-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="f801e-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="f801e-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f801e-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f801e-128">Показывает, реализует ли метод операцию, которая может инициировать сеанс на сервере.</span><span class="sxs-lookup"><span data-stu-id="f801e-128">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="f801e-129">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="f801e-129">IsOneWay</span></span>  
 <span data-ttu-id="f801e-130">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="f801e-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="f801e-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f801e-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f801e-132">Показывает, возвращает ли операция ответное сообщение.</span><span class="sxs-lookup"><span data-stu-id="f801e-132">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="f801e-133">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="f801e-133">IsTerminating</span></span>  
 <span data-ttu-id="f801e-134">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="f801e-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="f801e-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f801e-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f801e-136">Показывает, возвращает ли операция ответное сообщение.</span><span class="sxs-lookup"><span data-stu-id="f801e-136">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="f801e-137">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="f801e-137">MethodSignature</span></span>  
 <span data-ttu-id="f801e-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f801e-138">Data type: string</span></span>  
  
 <span data-ttu-id="f801e-139">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f801e-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f801e-140">Подпись метода операции.</span><span class="sxs-lookup"><span data-stu-id="f801e-140">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="f801e-141">Имя</span><span class="sxs-lookup"><span data-stu-id="f801e-141">Name</span></span>  
 <span data-ttu-id="f801e-142">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f801e-142">Data type: string</span></span>  
  
 <span data-ttu-id="f801e-143">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f801e-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f801e-144">Имя операции.</span><span class="sxs-lookup"><span data-stu-id="f801e-144">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="f801e-145">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="f801e-145">ParameterTypes</span></span>  
 <span data-ttu-id="f801e-146">Тип данных: массив строк</span><span class="sxs-lookup"><span data-stu-id="f801e-146">Data type: string array</span></span>  
  
 <span data-ttu-id="f801e-147">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f801e-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f801e-148">Типы параметров операции.</span><span class="sxs-lookup"><span data-stu-id="f801e-148">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="f801e-149">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="f801e-149">ReplyAction</span></span>  
 <span data-ttu-id="f801e-150">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f801e-150">Data type: string</span></span>  
  
 <span data-ttu-id="f801e-151">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f801e-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f801e-152">Значение действия SOAP для ответного сообщения операции.</span><span class="sxs-lookup"><span data-stu-id="f801e-152">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="f801e-153">ReturnType</span><span class="sxs-lookup"><span data-stu-id="f801e-153">ReturnType</span></span>  
 <span data-ttu-id="f801e-154">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="f801e-154">Data type: string</span></span>  
  
 <span data-ttu-id="f801e-155">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f801e-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f801e-156">Возвращаемый тип операции.</span><span class="sxs-lookup"><span data-stu-id="f801e-156">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f801e-157">Требования</span><span class="sxs-lookup"><span data-stu-id="f801e-157">Requirements</span></span>  
  
|<span data-ttu-id="f801e-158">MOF</span><span class="sxs-lookup"><span data-stu-id="f801e-158">MOF</span></span>|<span data-ttu-id="f801e-159">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f801e-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f801e-160">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="f801e-160">Namespace</span></span>|<span data-ttu-id="f801e-161">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="f801e-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f801e-162">См. также</span><span class="sxs-lookup"><span data-stu-id="f801e-162">See Also</span></span>  
 <xref:System.ServiceModel.Description.OperationDescription>
