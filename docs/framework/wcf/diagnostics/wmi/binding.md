---
title: Binding2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b9e44d161e1229db9145f4ed7e337396bbd98c68
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="binding"></a><span data-ttu-id="479a6-102">Привязка</span><span class="sxs-lookup"><span data-stu-id="479a6-102">Binding</span></span>
<span data-ttu-id="479a6-103">wmi Binding</span><span class="sxs-lookup"><span data-stu-id="479a6-103">wmi Binding</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="479a6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="479a6-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="479a6-105">Методы</span><span class="sxs-lookup"><span data-stu-id="479a6-105">Methods</span></span>  
 <span data-ttu-id="479a6-106">Класс Binding не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="479a6-106">The Binding class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="479a6-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="479a6-107">Properties</span></span>  
 <span data-ttu-id="479a6-108">Класс Binding имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="479a6-108">The Binding class has the following properties.</span></span>  
  
### <a name="bindingelements"></a><span data-ttu-id="479a6-109">BindingElements</span><span class="sxs-lookup"><span data-stu-id="479a6-109">BindingElements</span></span>  
 <span data-ttu-id="479a6-110">Тип данных: массив BindingElement</span><span class="sxs-lookup"><span data-stu-id="479a6-110">Data type: BindingElement array</span></span>  
  
 <span data-ttu-id="479a6-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="479a6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="479a6-112">Коллекция элементов привязки, реализованных привязкой.</span><span class="sxs-lookup"><span data-stu-id="479a6-112">The collection of binding elements implemented by the binding.</span></span>  
  
### <a name="closetimeout"></a><span data-ttu-id="479a6-113">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="479a6-113">CloseTimeout</span></span>  
 <span data-ttu-id="479a6-114">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="479a6-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="479a6-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="479a6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="479a6-116">Интервал времени, предусмотренный для завершения операции закрытия.</span><span class="sxs-lookup"><span data-stu-id="479a6-116">The interval of time provided for a close operation to complete.</span></span>  
  
### <a name="name"></a><span data-ttu-id="479a6-117">Имя</span><span class="sxs-lookup"><span data-stu-id="479a6-117">Name</span></span>  
 <span data-ttu-id="479a6-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="479a6-118">Data type: string</span></span>  
  
 <span data-ttu-id="479a6-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="479a6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="479a6-120">Имя привязки.</span><span class="sxs-lookup"><span data-stu-id="479a6-120">The name of the binding.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="479a6-121">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="479a6-121">Namespace</span></span>  
 <span data-ttu-id="479a6-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="479a6-122">Data type: string</span></span>  
  
 <span data-ttu-id="479a6-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="479a6-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="479a6-124">Пространство имен XML привязки.</span><span class="sxs-lookup"><span data-stu-id="479a6-124">The XML namespace of the binding.</span></span>  
  
### <a name="opentimeout"></a><span data-ttu-id="479a6-125">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="479a6-125">OpenTimeout</span></span>  
 <span data-ttu-id="479a6-126">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="479a6-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="479a6-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="479a6-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="479a6-128">Интервал времени, предусмотренный для завершения операции открытия.</span><span class="sxs-lookup"><span data-stu-id="479a6-128">The interval of time provided for an open operation to complete.</span></span>  
  
### <a name="receivetimeout"></a><span data-ttu-id="479a6-129">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="479a6-129">ReceiveTimeout</span></span>  
 <span data-ttu-id="479a6-130">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="479a6-130">Data type: datetime</span></span>  
  
 <span data-ttu-id="479a6-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="479a6-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="479a6-132">Интервал времени, предусмотренный для завершения операции получения.</span><span class="sxs-lookup"><span data-stu-id="479a6-132">The interval of time provided for a receive operation to complete.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="479a6-133">Схема</span><span class="sxs-lookup"><span data-stu-id="479a6-133">Scheme</span></span>  
 <span data-ttu-id="479a6-134">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="479a6-134">Data type: string</span></span>  
  
 <span data-ttu-id="479a6-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="479a6-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="479a6-136">Схема транспорта универсальных кодов ресурсов (URI), которая используется производствами каналов и прослушивателей, созданными привязкой.</span><span class="sxs-lookup"><span data-stu-id="479a6-136">The URI transport scheme that is used by the channel and listener factories that are built by the binding.</span></span>  
  
### <a name="sendtimeout"></a><span data-ttu-id="479a6-137">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="479a6-137">SendTimeout</span></span>  
 <span data-ttu-id="479a6-138">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="479a6-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="479a6-139">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="479a6-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="479a6-140">Интервал времени, предусмотренный для завершения операции отправки.</span><span class="sxs-lookup"><span data-stu-id="479a6-140">The interval of time provided for a send operation to complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="479a6-141">Требования</span><span class="sxs-lookup"><span data-stu-id="479a6-141">Requirements</span></span>  
  
|<span data-ttu-id="479a6-142">MOF</span><span class="sxs-lookup"><span data-stu-id="479a6-142">MOF</span></span>|<span data-ttu-id="479a6-143">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="479a6-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="479a6-144">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="479a6-144">Namespace</span></span>|<span data-ttu-id="479a6-145">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="479a6-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="479a6-146">См. также</span><span class="sxs-lookup"><span data-stu-id="479a6-146">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>
