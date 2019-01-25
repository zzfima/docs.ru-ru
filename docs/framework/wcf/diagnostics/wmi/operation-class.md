---
title: Класс Operation
ms.date: 03/30/2017
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
ms.openlocfilehash: 9453d67854bb8439891661b07e3ab3aa373e23eb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668305"
---
# <a name="operation-class"></a><span data-ttu-id="370f8-102">Класс Operation</span><span class="sxs-lookup"><span data-stu-id="370f8-102">Operation class</span></span>
<span data-ttu-id="370f8-103">Операция</span><span class="sxs-lookup"><span data-stu-id="370f8-103">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="370f8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="370f8-104">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="370f8-105">Методы</span><span class="sxs-lookup"><span data-stu-id="370f8-105">Methods</span></span>  
 <span data-ttu-id="370f8-106">Класс Operation не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="370f8-106">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="370f8-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="370f8-107">Properties</span></span>  
 <span data-ttu-id="370f8-108">Класс Operation имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="370f8-108">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="370f8-109">Действие</span><span class="sxs-lookup"><span data-stu-id="370f8-109">Action</span></span>  
 <span data-ttu-id="370f8-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="370f8-110">Data type: string</span></span>  
  
 <span data-ttu-id="370f8-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="370f8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="370f8-112">Действие WS-Addressing сообщения запроса.</span><span class="sxs-lookup"><span data-stu-id="370f8-112">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="370f8-113">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="370f8-113">AsyncPattern</span></span>  
 <span data-ttu-id="370f8-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="370f8-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="370f8-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="370f8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="370f8-116">Указывает, что операция реализуется асинхронно с помощью `Begin`[открыть/закрыть угловые скобки] и `End`пары методов [открыть/закрыть угловые скобки] в контракте службы.</span><span class="sxs-lookup"><span data-stu-id="370f8-116">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="370f8-117">поведения</span><span class="sxs-lookup"><span data-stu-id="370f8-117">Behaviors</span></span>  
 <span data-ttu-id="370f8-118">Тип данных: Массив Behavior</span><span class="sxs-lookup"><span data-stu-id="370f8-118">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="370f8-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="370f8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="370f8-120">Поведения, связанные с этой операцией.</span><span class="sxs-lookup"><span data-stu-id="370f8-120">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="370f8-121">IsCallback</span><span class="sxs-lookup"><span data-stu-id="370f8-121">IsCallback</span></span>  
 <span data-ttu-id="370f8-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="370f8-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="370f8-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="370f8-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="370f8-124">Истинно, если операция является операцией обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="370f8-124">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="370f8-125">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="370f8-125">IsInitiating</span></span>  
 <span data-ttu-id="370f8-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="370f8-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="370f8-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="370f8-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="370f8-128">Показывает, реализует ли метод операцию, которая может инициировать сеанс на сервере.</span><span class="sxs-lookup"><span data-stu-id="370f8-128">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="370f8-129">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="370f8-129">IsOneWay</span></span>  
 <span data-ttu-id="370f8-130">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="370f8-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="370f8-131">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="370f8-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="370f8-132">Показывает, возвращает ли операция ответное сообщение.</span><span class="sxs-lookup"><span data-stu-id="370f8-132">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="370f8-133">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="370f8-133">IsTerminating</span></span>  
 <span data-ttu-id="370f8-134">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="370f8-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="370f8-135">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="370f8-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="370f8-136">Показывает, возвращает ли операция ответное сообщение.</span><span class="sxs-lookup"><span data-stu-id="370f8-136">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="370f8-137">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="370f8-137">MethodSignature</span></span>  
 <span data-ttu-id="370f8-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="370f8-138">Data type: string</span></span>  
  
 <span data-ttu-id="370f8-139">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="370f8-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="370f8-140">Подпись метода операции.</span><span class="sxs-lookup"><span data-stu-id="370f8-140">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="370f8-141">name</span><span class="sxs-lookup"><span data-stu-id="370f8-141">Name</span></span>  
 <span data-ttu-id="370f8-142">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="370f8-142">Data type: string</span></span>  
  
 <span data-ttu-id="370f8-143">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="370f8-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="370f8-144">Имя операции.</span><span class="sxs-lookup"><span data-stu-id="370f8-144">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="370f8-145">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="370f8-145">ParameterTypes</span></span>  
 <span data-ttu-id="370f8-146">Тип данных: массив строк</span><span class="sxs-lookup"><span data-stu-id="370f8-146">Data type: string array</span></span>  
  
 <span data-ttu-id="370f8-147">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="370f8-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="370f8-148">Типы параметров операции.</span><span class="sxs-lookup"><span data-stu-id="370f8-148">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="370f8-149">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="370f8-149">ReplyAction</span></span>  
 <span data-ttu-id="370f8-150">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="370f8-150">Data type: string</span></span>  
  
 <span data-ttu-id="370f8-151">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="370f8-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="370f8-152">Значение действия SOAP для ответного сообщения операции.</span><span class="sxs-lookup"><span data-stu-id="370f8-152">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="370f8-153">ReturnType</span><span class="sxs-lookup"><span data-stu-id="370f8-153">ReturnType</span></span>  
 <span data-ttu-id="370f8-154">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="370f8-154">Data type: string</span></span>  
  
 <span data-ttu-id="370f8-155">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="370f8-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="370f8-156">Тип возвращаемого значения операции.</span><span class="sxs-lookup"><span data-stu-id="370f8-156">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="370f8-157">Требования</span><span class="sxs-lookup"><span data-stu-id="370f8-157">Requirements</span></span>  
  
|<span data-ttu-id="370f8-158">MOF</span><span class="sxs-lookup"><span data-stu-id="370f8-158">MOF</span></span>|<span data-ttu-id="370f8-159">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="370f8-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="370f8-160">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="370f8-160">Namespace</span></span>|<span data-ttu-id="370f8-161">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="370f8-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="370f8-162">См. также</span><span class="sxs-lookup"><span data-stu-id="370f8-162">See also</span></span>
- <xref:System.ServiceModel.Description.OperationDescription>
