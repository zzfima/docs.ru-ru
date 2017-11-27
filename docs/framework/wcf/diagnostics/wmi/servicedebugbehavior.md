---
title: ServiceDebugBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2d6b866c90e3e6c6e72dc75f230bcf7b4e03a6bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="servicedebugbehavior"></a><span data-ttu-id="4be83-102">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="4be83-102">ServiceDebugBehavior</span></span>
<span data-ttu-id="4be83-103">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="4be83-103">ServiceDebugBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4be83-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4be83-104">Syntax</span></span>  
  
```  
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4be83-105">Методы</span><span class="sxs-lookup"><span data-stu-id="4be83-105">Methods</span></span>  
 <span data-ttu-id="4be83-106">Класс ServiceDebugBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="4be83-106">The ServiceDebugBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4be83-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="4be83-107">Properties</span></span>  
 <span data-ttu-id="4be83-108">Класс ServiceDebugBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="4be83-108">The ServiceDebugBehavior class has the following properties:</span></span>  
  
### <a name="httphelppageenabled"></a><span data-ttu-id="4be83-109">HttpHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="4be83-109">HttpHelpPageEnabled</span></span>  
 <span data-ttu-id="4be83-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="4be83-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="4be83-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="4be83-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4be83-112">Определяет, публикует ли служба свой код WSDL по адресу, определяемому атрибутом `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="4be83-112">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httphelppageurl"></a><span data-ttu-id="4be83-113">HttpHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="4be83-113">HttpHelpPageUrl</span></span>  
 <span data-ttu-id="4be83-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="4be83-114">Data type: string</span></span>  
  
 <span data-ttu-id="4be83-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="4be83-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4be83-116">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTP.</span><span class="sxs-lookup"><span data-stu-id="4be83-116">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpshelppageenabled"></a><span data-ttu-id="4be83-117">HttpsHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="4be83-117">HttpsHelpPageEnabled</span></span>  
 <span data-ttu-id="4be83-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="4be83-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="4be83-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="4be83-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4be83-120">Определяет, публикует ли служба свой язык WSDL через HTTPS по адресу, указанному в атрибуте `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="4be83-120">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpshelppageurl"></a><span data-ttu-id="4be83-121">HttpsHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="4be83-121">HttpsHelpPageUrl</span></span>  
 <span data-ttu-id="4be83-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="4be83-122">Data type: string</span></span>  
  
 <span data-ttu-id="4be83-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="4be83-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4be83-124">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4be83-124">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="4be83-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="4be83-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="4be83-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="4be83-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="4be83-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="4be83-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4be83-128">Указывает, включать ли информацию об управляемых исключениях в сведения об ошибках SOAP, возвращаемые клиентам для отладки.</span><span class="sxs-lookup"><span data-stu-id="4be83-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4be83-129">Требования</span><span class="sxs-lookup"><span data-stu-id="4be83-129">Requirements</span></span>  
  
|<span data-ttu-id="4be83-130">MOF</span><span class="sxs-lookup"><span data-stu-id="4be83-130">MOF</span></span>|<span data-ttu-id="4be83-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4be83-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4be83-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="4be83-132">Namespace</span></span>|<span data-ttu-id="4be83-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="4be83-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4be83-134">См. также</span><span class="sxs-lookup"><span data-stu-id="4be83-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceDebugBehavior>
