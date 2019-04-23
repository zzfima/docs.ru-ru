---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 1d99af064205447c2f11f6f19258551c1e88d386
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59976142"
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="299e6-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="299e6-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="299e6-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="299e6-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="299e6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="299e6-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="299e6-105">Методы</span><span class="sxs-lookup"><span data-stu-id="299e6-105">Methods</span></span>  
 <span data-ttu-id="299e6-106">Класс ServiceMetadataBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="299e6-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="299e6-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="299e6-107">Properties</span></span>  
 <span data-ttu-id="299e6-108">Класс ServiceMetadataBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="299e6-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="299e6-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="299e6-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="299e6-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="299e6-110">Data type: string</span></span>  
  
 <span data-ttu-id="299e6-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="299e6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="299e6-112">Задает расположение, в которое служба перенаправляет запросы метаданных.</span><span class="sxs-lookup"><span data-stu-id="299e6-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="299e6-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="299e6-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="299e6-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="299e6-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="299e6-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="299e6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="299e6-116">Определяет, публикует ли служба свой код WSDL по адресу, определяемому атрибутом `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="299e6-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="299e6-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="299e6-117">HttpGetUrl</span></span>  
 <span data-ttu-id="299e6-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="299e6-118">Data type: string</span></span>  
  
 <span data-ttu-id="299e6-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="299e6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="299e6-120">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTP.</span><span class="sxs-lookup"><span data-stu-id="299e6-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="299e6-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="299e6-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="299e6-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="299e6-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="299e6-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="299e6-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="299e6-124">Определяет, публикует ли служба свой язык WSDL через HTTPS по адресу, указанному в атрибуте `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="299e6-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="299e6-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="299e6-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="299e6-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="299e6-126">Data type: string</span></span>  
  
 <span data-ttu-id="299e6-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="299e6-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="299e6-128">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTPS.</span><span class="sxs-lookup"><span data-stu-id="299e6-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="299e6-129">Требования</span><span class="sxs-lookup"><span data-stu-id="299e6-129">Requirements</span></span>  
  
|<span data-ttu-id="299e6-130">MOF</span><span class="sxs-lookup"><span data-stu-id="299e6-130">MOF</span></span>|<span data-ttu-id="299e6-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="299e6-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="299e6-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="299e6-132">Namespace</span></span>|<span data-ttu-id="299e6-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="299e6-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="299e6-134">См. также</span><span class="sxs-lookup"><span data-stu-id="299e6-134">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
