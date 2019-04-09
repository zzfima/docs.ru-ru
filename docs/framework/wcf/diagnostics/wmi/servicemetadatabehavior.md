---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 1d99af064205447c2f11f6f19258551c1e88d386
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160333"
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="1e92f-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="1e92f-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="1e92f-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="1e92f-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e92f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e92f-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="1e92f-105">Методы</span><span class="sxs-lookup"><span data-stu-id="1e92f-105">Methods</span></span>  
 <span data-ttu-id="1e92f-106">Класс ServiceMetadataBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="1e92f-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1e92f-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="1e92f-107">Properties</span></span>  
 <span data-ttu-id="1e92f-108">Класс ServiceMetadataBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="1e92f-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="1e92f-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="1e92f-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="1e92f-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="1e92f-110">Data type: string</span></span>  
  
 <span data-ttu-id="1e92f-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="1e92f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1e92f-112">Задает расположение, в которое служба перенаправляет запросы метаданных.</span><span class="sxs-lookup"><span data-stu-id="1e92f-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="1e92f-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="1e92f-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="1e92f-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="1e92f-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="1e92f-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="1e92f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1e92f-116">Определяет, публикует ли служба свой код WSDL по адресу, определяемому атрибутом `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="1e92f-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="1e92f-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="1e92f-117">HttpGetUrl</span></span>  
 <span data-ttu-id="1e92f-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="1e92f-118">Data type: string</span></span>  
  
 <span data-ttu-id="1e92f-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="1e92f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1e92f-120">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTP.</span><span class="sxs-lookup"><span data-stu-id="1e92f-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="1e92f-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="1e92f-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="1e92f-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="1e92f-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="1e92f-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="1e92f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1e92f-124">Определяет, публикует ли служба свой язык WSDL через HTTPS по адресу, указанному в атрибуте `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="1e92f-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="1e92f-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="1e92f-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="1e92f-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="1e92f-126">Data type: string</span></span>  
  
 <span data-ttu-id="1e92f-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="1e92f-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1e92f-128">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1e92f-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e92f-129">Требования</span><span class="sxs-lookup"><span data-stu-id="1e92f-129">Requirements</span></span>  
  
|<span data-ttu-id="1e92f-130">MOF</span><span class="sxs-lookup"><span data-stu-id="1e92f-130">MOF</span></span>|<span data-ttu-id="1e92f-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="1e92f-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1e92f-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="1e92f-132">Namespace</span></span>|<span data-ttu-id="1e92f-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="1e92f-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1e92f-134">См. также</span><span class="sxs-lookup"><span data-stu-id="1e92f-134">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
