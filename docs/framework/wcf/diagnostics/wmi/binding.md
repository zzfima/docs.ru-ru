---
title: Binding2
ms.date: 03/30/2017
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
ms.openlocfilehash: a040cc6e12833d2c737eb14c591300e5873ddce7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979164"
---
# <a name="binding"></a><span data-ttu-id="1b7de-102">Привязка</span><span class="sxs-lookup"><span data-stu-id="1b7de-102">Binding</span></span>
<span data-ttu-id="1b7de-103">wmi Binding</span><span class="sxs-lookup"><span data-stu-id="1b7de-103">wmi Binding</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b7de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1b7de-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="1b7de-105">Методы</span><span class="sxs-lookup"><span data-stu-id="1b7de-105">Methods</span></span>  
 <span data-ttu-id="1b7de-106">Класс Binding не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="1b7de-106">The Binding class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1b7de-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="1b7de-107">Properties</span></span>  
 <span data-ttu-id="1b7de-108">Класс Binding имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="1b7de-108">The Binding class has the following properties.</span></span>  
  
### <a name="bindingelements"></a><span data-ttu-id="1b7de-109">BindingElements</span><span class="sxs-lookup"><span data-stu-id="1b7de-109">BindingElements</span></span>  
 <span data-ttu-id="1b7de-110">Тип данных: Массив BindingElement</span><span class="sxs-lookup"><span data-stu-id="1b7de-110">Data type: BindingElement array</span></span>  
  
 <span data-ttu-id="1b7de-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="1b7de-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1b7de-112">Коллекция элементов привязки, реализованных привязкой.</span><span class="sxs-lookup"><span data-stu-id="1b7de-112">The collection of binding elements implemented by the binding.</span></span>  
  
### <a name="closetimeout"></a><span data-ttu-id="1b7de-113">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="1b7de-113">CloseTimeout</span></span>  
 <span data-ttu-id="1b7de-114">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="1b7de-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="1b7de-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="1b7de-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1b7de-116">Интервал времени, предусмотренный для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="1b7de-116">The interval of time provided for a close operation to complete.</span></span>  
  
### <a name="name"></a><span data-ttu-id="1b7de-117">name</span><span class="sxs-lookup"><span data-stu-id="1b7de-117">Name</span></span>  
 <span data-ttu-id="1b7de-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="1b7de-118">Data type: string</span></span>  
  
 <span data-ttu-id="1b7de-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="1b7de-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1b7de-120">Имя привязки.</span><span class="sxs-lookup"><span data-stu-id="1b7de-120">The name of the binding.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="1b7de-121">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="1b7de-121">Namespace</span></span>  
 <span data-ttu-id="1b7de-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="1b7de-122">Data type: string</span></span>  
  
 <span data-ttu-id="1b7de-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="1b7de-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1b7de-124">Пространство имен XML привязки.</span><span class="sxs-lookup"><span data-stu-id="1b7de-124">The XML namespace of the binding.</span></span>  
  
### <a name="opentimeout"></a><span data-ttu-id="1b7de-125">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="1b7de-125">OpenTimeout</span></span>  
 <span data-ttu-id="1b7de-126">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="1b7de-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="1b7de-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="1b7de-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1b7de-128">Интервал времени, предусмотренный для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="1b7de-128">The interval of time provided for an open operation to complete.</span></span>  
  
### <a name="receivetimeout"></a><span data-ttu-id="1b7de-129">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="1b7de-129">ReceiveTimeout</span></span>  
 <span data-ttu-id="1b7de-130">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="1b7de-130">Data type: datetime</span></span>  
  
 <span data-ttu-id="1b7de-131">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="1b7de-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1b7de-132">Интервал времени, предусмотренный для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="1b7de-132">The interval of time provided for a receive operation to complete.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="1b7de-133">Схема</span><span class="sxs-lookup"><span data-stu-id="1b7de-133">Scheme</span></span>  
 <span data-ttu-id="1b7de-134">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="1b7de-134">Data type: string</span></span>  
  
 <span data-ttu-id="1b7de-135">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="1b7de-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1b7de-136">Схема транспорта универсальных кодов ресурсов (URI), которая используется производствами каналов и прослушивателей, созданными привязкой.</span><span class="sxs-lookup"><span data-stu-id="1b7de-136">The URI transport scheme that is used by the channel and listener factories that are built by the binding.</span></span>  
  
### <a name="sendtimeout"></a><span data-ttu-id="1b7de-137">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="1b7de-137">SendTimeout</span></span>  
 <span data-ttu-id="1b7de-138">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="1b7de-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="1b7de-139">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="1b7de-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1b7de-140">Интервал времени, предусмотренный для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="1b7de-140">The interval of time provided for a send operation to complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b7de-141">Требования</span><span class="sxs-lookup"><span data-stu-id="1b7de-141">Requirements</span></span>  
  
|<span data-ttu-id="1b7de-142">MOF</span><span class="sxs-lookup"><span data-stu-id="1b7de-142">MOF</span></span>|<span data-ttu-id="1b7de-143">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="1b7de-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1b7de-144">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="1b7de-144">Namespace</span></span>|<span data-ttu-id="1b7de-145">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="1b7de-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1b7de-146">См. также</span><span class="sxs-lookup"><span data-stu-id="1b7de-146">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
