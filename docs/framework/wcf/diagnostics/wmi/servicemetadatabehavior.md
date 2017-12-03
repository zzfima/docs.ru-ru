---
title: ServiceMetadataBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f17b31e1dfe9ba60b2042a85a6d673d986fe0a33
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="954ff-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="954ff-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="954ff-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="954ff-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="954ff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="954ff-104">Syntax</span></span>  
  
```  
class ServiceMetadataBehavior : Behavior  
{  
  string ExternalMetadataLocation;  
  boolean HttpGetEnabled;  
  string HttpGetUrl;  
  boolean HttpsGetEnabled;  
  string HttpsGetUrl;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="954ff-105">Методы</span><span class="sxs-lookup"><span data-stu-id="954ff-105">Methods</span></span>  
 <span data-ttu-id="954ff-106">Класс ServiceMetadataBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="954ff-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="954ff-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="954ff-107">Properties</span></span>  
 <span data-ttu-id="954ff-108">Класс ServiceMetadataBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="954ff-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="954ff-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="954ff-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="954ff-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="954ff-110">Data type: string</span></span>  
  
 <span data-ttu-id="954ff-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="954ff-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="954ff-112">Задает расположение, в которое служба перенаправляет запросы метаданных.</span><span class="sxs-lookup"><span data-stu-id="954ff-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="954ff-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="954ff-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="954ff-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="954ff-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="954ff-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="954ff-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="954ff-116">Определяет, публикует ли служба свой код WSDL по адресу, определяемому атрибутом `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="954ff-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="954ff-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="954ff-117">HttpGetUrl</span></span>  
 <span data-ttu-id="954ff-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="954ff-118">Data type: string</span></span>  
  
 <span data-ttu-id="954ff-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="954ff-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="954ff-120">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTP.</span><span class="sxs-lookup"><span data-stu-id="954ff-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="954ff-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="954ff-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="954ff-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="954ff-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="954ff-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="954ff-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="954ff-124">Определяет, публикует ли служба свой язык WSDL через HTTPS по адресу, указанному в атрибуте `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="954ff-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="954ff-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="954ff-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="954ff-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="954ff-126">Data type: string</span></span>  
  
 <span data-ttu-id="954ff-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="954ff-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="954ff-128">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTPS.</span><span class="sxs-lookup"><span data-stu-id="954ff-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="954ff-129">Требования</span><span class="sxs-lookup"><span data-stu-id="954ff-129">Requirements</span></span>  
  
|<span data-ttu-id="954ff-130">MOF</span><span class="sxs-lookup"><span data-stu-id="954ff-130">MOF</span></span>|<span data-ttu-id="954ff-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="954ff-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="954ff-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="954ff-132">Namespace</span></span>|<span data-ttu-id="954ff-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="954ff-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="954ff-134">См. также</span><span class="sxs-lookup"><span data-stu-id="954ff-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
