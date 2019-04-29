---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 1d99af064205447c2f11f6f19258551c1e88d386
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956953"
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="cf3f0-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="cf3f0-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="cf3f0-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="cf3f0-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf3f0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf3f0-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="cf3f0-105">Методы</span><span class="sxs-lookup"><span data-stu-id="cf3f0-105">Methods</span></span>  
 <span data-ttu-id="cf3f0-106">Класс ServiceMetadataBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="cf3f0-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="cf3f0-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="cf3f0-107">Properties</span></span>  
 <span data-ttu-id="cf3f0-108">Класс ServiceMetadataBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="cf3f0-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="cf3f0-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="cf3f0-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="cf3f0-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="cf3f0-110">Data type: string</span></span>  
  
 <span data-ttu-id="cf3f0-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="cf3f0-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf3f0-112">Задает расположение, в которое служба перенаправляет запросы метаданных.</span><span class="sxs-lookup"><span data-stu-id="cf3f0-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="cf3f0-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="cf3f0-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="cf3f0-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="cf3f0-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="cf3f0-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="cf3f0-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf3f0-116">Определяет, публикует ли служба свой код WSDL по адресу, определяемому атрибутом `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="cf3f0-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="cf3f0-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="cf3f0-117">HttpGetUrl</span></span>  
 <span data-ttu-id="cf3f0-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="cf3f0-118">Data type: string</span></span>  
  
 <span data-ttu-id="cf3f0-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="cf3f0-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf3f0-120">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTP.</span><span class="sxs-lookup"><span data-stu-id="cf3f0-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="cf3f0-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="cf3f0-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="cf3f0-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="cf3f0-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="cf3f0-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="cf3f0-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf3f0-124">Определяет, публикует ли служба свой язык WSDL через HTTPS по адресу, указанному в атрибуте `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="cf3f0-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="cf3f0-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="cf3f0-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="cf3f0-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="cf3f0-126">Data type: string</span></span>  
  
 <span data-ttu-id="cf3f0-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="cf3f0-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf3f0-128">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cf3f0-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf3f0-129">Требования</span><span class="sxs-lookup"><span data-stu-id="cf3f0-129">Requirements</span></span>  
  
|<span data-ttu-id="cf3f0-130">MOF</span><span class="sxs-lookup"><span data-stu-id="cf3f0-130">MOF</span></span>|<span data-ttu-id="cf3f0-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="cf3f0-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="cf3f0-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="cf3f0-132">Namespace</span></span>|<span data-ttu-id="cf3f0-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="cf3f0-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cf3f0-134">См. также</span><span class="sxs-lookup"><span data-stu-id="cf3f0-134">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
