---
title: Binding2
ms.date: 03/30/2017
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
ms.openlocfilehash: a040cc6e12833d2c737eb14c591300e5873ddce7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106526"
---
# <a name="binding"></a><span data-ttu-id="de801-102">Привязка</span><span class="sxs-lookup"><span data-stu-id="de801-102">Binding</span></span>
<span data-ttu-id="de801-103">wmi Binding</span><span class="sxs-lookup"><span data-stu-id="de801-103">wmi Binding</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de801-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="de801-104">Syntax</span></span>  
  
```csharp
class Binding  
{  
  BindingElement BindingElements[];  
  datetime CloseTimeout;  
  string Name;  
  string Namespace;  
  datetime OpenTimeout;  
  datetime ReceiveTimeout;  
  string Scheme;  
  datetime SendTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="de801-105">Методы</span><span class="sxs-lookup"><span data-stu-id="de801-105">Methods</span></span>  
 <span data-ttu-id="de801-106">Класс Binding не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="de801-106">The Binding class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="de801-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="de801-107">Properties</span></span>  
 <span data-ttu-id="de801-108">Класс Binding имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="de801-108">The Binding class has the following properties.</span></span>  
  
### <a name="bindingelements"></a><span data-ttu-id="de801-109">BindingElements</span><span class="sxs-lookup"><span data-stu-id="de801-109">BindingElements</span></span>  
 <span data-ttu-id="de801-110">Тип данных: Массив BindingElement</span><span class="sxs-lookup"><span data-stu-id="de801-110">Data type: BindingElement array</span></span>  
  
 <span data-ttu-id="de801-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="de801-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="de801-112">Коллекция элементов привязки, реализованных привязкой.</span><span class="sxs-lookup"><span data-stu-id="de801-112">The collection of binding elements implemented by the binding.</span></span>  
  
### <a name="closetimeout"></a><span data-ttu-id="de801-113">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="de801-113">CloseTimeout</span></span>  
 <span data-ttu-id="de801-114">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="de801-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="de801-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="de801-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="de801-116">Интервал времени, предусмотренный для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="de801-116">The interval of time provided for a close operation to complete.</span></span>  
  
### <a name="name"></a><span data-ttu-id="de801-117">name</span><span class="sxs-lookup"><span data-stu-id="de801-117">Name</span></span>  
 <span data-ttu-id="de801-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="de801-118">Data type: string</span></span>  
  
 <span data-ttu-id="de801-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="de801-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="de801-120">Имя привязки.</span><span class="sxs-lookup"><span data-stu-id="de801-120">The name of the binding.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="de801-121">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="de801-121">Namespace</span></span>  
 <span data-ttu-id="de801-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="de801-122">Data type: string</span></span>  
  
 <span data-ttu-id="de801-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="de801-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="de801-124">Пространство имен XML привязки.</span><span class="sxs-lookup"><span data-stu-id="de801-124">The XML namespace of the binding.</span></span>  
  
### <a name="opentimeout"></a><span data-ttu-id="de801-125">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="de801-125">OpenTimeout</span></span>  
 <span data-ttu-id="de801-126">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="de801-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="de801-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="de801-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="de801-128">Интервал времени, предусмотренный для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="de801-128">The interval of time provided for an open operation to complete.</span></span>  
  
### <a name="receivetimeout"></a><span data-ttu-id="de801-129">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="de801-129">ReceiveTimeout</span></span>  
 <span data-ttu-id="de801-130">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="de801-130">Data type: datetime</span></span>  
  
 <span data-ttu-id="de801-131">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="de801-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="de801-132">Интервал времени, предусмотренный для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="de801-132">The interval of time provided for a receive operation to complete.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="de801-133">Схема</span><span class="sxs-lookup"><span data-stu-id="de801-133">Scheme</span></span>  
 <span data-ttu-id="de801-134">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="de801-134">Data type: string</span></span>  
  
 <span data-ttu-id="de801-135">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="de801-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="de801-136">Схема транспорта универсальных кодов ресурсов (URI), которая используется производствами каналов и прослушивателей, созданными привязкой.</span><span class="sxs-lookup"><span data-stu-id="de801-136">The URI transport scheme that is used by the channel and listener factories that are built by the binding.</span></span>  
  
### <a name="sendtimeout"></a><span data-ttu-id="de801-137">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="de801-137">SendTimeout</span></span>  
 <span data-ttu-id="de801-138">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="de801-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="de801-139">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="de801-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="de801-140">Интервал времени, предусмотренный для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="de801-140">The interval of time provided for a send operation to complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de801-141">Требования</span><span class="sxs-lookup"><span data-stu-id="de801-141">Requirements</span></span>  
  
|<span data-ttu-id="de801-142">MOF</span><span class="sxs-lookup"><span data-stu-id="de801-142">MOF</span></span>|<span data-ttu-id="de801-143">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="de801-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="de801-144">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="de801-144">Namespace</span></span>|<span data-ttu-id="de801-145">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="de801-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="de801-146">См. также</span><span class="sxs-lookup"><span data-stu-id="de801-146">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
