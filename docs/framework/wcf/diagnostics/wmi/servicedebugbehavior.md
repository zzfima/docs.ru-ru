---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: 68b2350f257bc95d8e17f4b9049d67c7f67becae
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452866"
---
# <a name="servicedebugbehavior"></a><span data-ttu-id="64961-102">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="64961-102">ServiceDebugBehavior</span></span>
<span data-ttu-id="64961-103">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="64961-103">ServiceDebugBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64961-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64961-104">Syntax</span></span>  
  
```csharp
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="64961-105">Методы</span><span class="sxs-lookup"><span data-stu-id="64961-105">Methods</span></span>  
 <span data-ttu-id="64961-106">Класс ServiceDebugBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="64961-106">The ServiceDebugBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="64961-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="64961-107">Properties</span></span>  
 <span data-ttu-id="64961-108">Класс ServiceDebugBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="64961-108">The ServiceDebugBehavior class has the following properties:</span></span>  
  
### <a name="httphelppageenabled"></a><span data-ttu-id="64961-109">HttpHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="64961-109">HttpHelpPageEnabled</span></span>  
 <span data-ttu-id="64961-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="64961-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="64961-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="64961-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="64961-112">Определяет, публикует ли служба свой код WSDL по адресу, определяемому атрибутом `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="64961-112">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httphelppageurl"></a><span data-ttu-id="64961-113">HttpHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="64961-113">HttpHelpPageUrl</span></span>  
 <span data-ttu-id="64961-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="64961-114">Data type: string</span></span>  
  
 <span data-ttu-id="64961-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="64961-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="64961-116">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTP.</span><span class="sxs-lookup"><span data-stu-id="64961-116">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpshelppageenabled"></a><span data-ttu-id="64961-117">HttpsHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="64961-117">HttpsHelpPageEnabled</span></span>  
 <span data-ttu-id="64961-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="64961-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="64961-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="64961-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="64961-120">Определяет, публикует ли служба свой язык WSDL через HTTPS по адресу, указанному в атрибуте `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="64961-120">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpshelppageurl"></a><span data-ttu-id="64961-121">HttpsHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="64961-121">HttpsHelpPageUrl</span></span>  
 <span data-ttu-id="64961-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="64961-122">Data type: string</span></span>  
  
 <span data-ttu-id="64961-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="64961-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="64961-124">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTPS.</span><span class="sxs-lookup"><span data-stu-id="64961-124">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="64961-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="64961-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="64961-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="64961-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="64961-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="64961-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="64961-128">Указывает, включать ли информацию об управляемых исключениях в сведения об ошибках SOAP, возвращаемые клиентам для отладки.</span><span class="sxs-lookup"><span data-stu-id="64961-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64961-129">Требования</span><span class="sxs-lookup"><span data-stu-id="64961-129">Requirements</span></span>  
  
|<span data-ttu-id="64961-130">MOF</span><span class="sxs-lookup"><span data-stu-id="64961-130">MOF</span></span>|<span data-ttu-id="64961-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="64961-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="64961-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="64961-132">Namespace</span></span>|<span data-ttu-id="64961-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="64961-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="64961-134">См. также</span><span class="sxs-lookup"><span data-stu-id="64961-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceDebugBehavior>
