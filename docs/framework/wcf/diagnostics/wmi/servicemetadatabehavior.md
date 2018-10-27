---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 19a04b6432f1ecc38a3b906b7e677175863134db
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188837"
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="d3d03-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="d3d03-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="d3d03-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="d3d03-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3d03-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3d03-104">Syntax</span></span>  
  
```csharp
class ServiceMetadataBehavior : Behavior  
{  
  string ExternalMetadataLocation;  
  boolean HttpGetEnabled;  
  string HttpGetUrl;  
  boolean HttpsGetEnabled;  
  string HttpsGetUrl;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d3d03-105">Методы</span><span class="sxs-lookup"><span data-stu-id="d3d03-105">Methods</span></span>  
 <span data-ttu-id="d3d03-106">Класс ServiceMetadataBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="d3d03-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d3d03-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="d3d03-107">Properties</span></span>  
 <span data-ttu-id="d3d03-108">Класс ServiceMetadataBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="d3d03-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="d3d03-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="d3d03-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="d3d03-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="d3d03-110">Data type: string</span></span>  
  
 <span data-ttu-id="d3d03-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d3d03-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d3d03-112">Задает расположение, в которое служба перенаправляет запросы метаданных.</span><span class="sxs-lookup"><span data-stu-id="d3d03-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="d3d03-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="d3d03-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="d3d03-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="d3d03-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="d3d03-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d3d03-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d3d03-116">Определяет, публикует ли служба свой код WSDL по адресу, определяемому атрибутом `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="d3d03-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="d3d03-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="d3d03-117">HttpGetUrl</span></span>  
 <span data-ttu-id="d3d03-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="d3d03-118">Data type: string</span></span>  
  
 <span data-ttu-id="d3d03-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d3d03-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d3d03-120">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTP.</span><span class="sxs-lookup"><span data-stu-id="d3d03-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="d3d03-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="d3d03-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="d3d03-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="d3d03-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="d3d03-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d3d03-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d3d03-124">Определяет, публикует ли служба свой язык WSDL через HTTPS по адресу, указанному в атрибуте `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="d3d03-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="d3d03-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="d3d03-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="d3d03-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="d3d03-126">Data type: string</span></span>  
  
 <span data-ttu-id="d3d03-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="d3d03-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d3d03-128">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d3d03-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3d03-129">Требования</span><span class="sxs-lookup"><span data-stu-id="d3d03-129">Requirements</span></span>  
  
|<span data-ttu-id="d3d03-130">MOF</span><span class="sxs-lookup"><span data-stu-id="d3d03-130">MOF</span></span>|<span data-ttu-id="d3d03-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d3d03-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d3d03-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="d3d03-132">Namespace</span></span>|<span data-ttu-id="d3d03-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="d3d03-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d3d03-134">См. также</span><span class="sxs-lookup"><span data-stu-id="d3d03-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
