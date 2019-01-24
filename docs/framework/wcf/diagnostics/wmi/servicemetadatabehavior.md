---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 76e28b18cd595a4a18f573dfe9539b646196c944
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720346"
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="015ee-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="015ee-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="015ee-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="015ee-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="015ee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="015ee-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="015ee-105">Методы</span><span class="sxs-lookup"><span data-stu-id="015ee-105">Methods</span></span>  
 <span data-ttu-id="015ee-106">Класс ServiceMetadataBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="015ee-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="015ee-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="015ee-107">Properties</span></span>  
 <span data-ttu-id="015ee-108">Класс ServiceMetadataBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="015ee-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="015ee-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="015ee-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="015ee-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="015ee-110">Data type: string</span></span>  
  
 <span data-ttu-id="015ee-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="015ee-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="015ee-112">Задает расположение, в которое служба перенаправляет запросы метаданных.</span><span class="sxs-lookup"><span data-stu-id="015ee-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="015ee-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="015ee-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="015ee-114">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="015ee-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="015ee-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="015ee-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="015ee-116">Определяет, публикует ли служба свой код WSDL по адресу, определяемому атрибутом `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="015ee-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="015ee-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="015ee-117">HttpGetUrl</span></span>  
 <span data-ttu-id="015ee-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="015ee-118">Data type: string</span></span>  
  
 <span data-ttu-id="015ee-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="015ee-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="015ee-120">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTP.</span><span class="sxs-lookup"><span data-stu-id="015ee-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="015ee-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="015ee-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="015ee-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="015ee-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="015ee-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="015ee-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="015ee-124">Определяет, публикует ли служба свой язык WSDL через HTTPS по адресу, указанному в атрибуте `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="015ee-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="015ee-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="015ee-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="015ee-126">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="015ee-126">Data type: string</span></span>  
  
 <span data-ttu-id="015ee-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="015ee-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="015ee-128">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTPS.</span><span class="sxs-lookup"><span data-stu-id="015ee-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="015ee-129">Требования</span><span class="sxs-lookup"><span data-stu-id="015ee-129">Requirements</span></span>  
  
|<span data-ttu-id="015ee-130">MOF</span><span class="sxs-lookup"><span data-stu-id="015ee-130">MOF</span></span>|<span data-ttu-id="015ee-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="015ee-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="015ee-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="015ee-132">Namespace</span></span>|<span data-ttu-id="015ee-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="015ee-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="015ee-134">См. также</span><span class="sxs-lookup"><span data-stu-id="015ee-134">See also</span></span>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
