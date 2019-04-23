---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: 2e38eb2c2d42ffc5436562b254a42215ccabbab2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59768661"
---
# <a name="servicedebugbehavior"></a><span data-ttu-id="4a04f-102">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="4a04f-102">ServiceDebugBehavior</span></span>
<span data-ttu-id="4a04f-103">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="4a04f-103">ServiceDebugBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a04f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a04f-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="4a04f-105">Методы</span><span class="sxs-lookup"><span data-stu-id="4a04f-105">Methods</span></span>  
 <span data-ttu-id="4a04f-106">Класс ServiceDebugBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="4a04f-106">The ServiceDebugBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4a04f-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="4a04f-107">Properties</span></span>  
 <span data-ttu-id="4a04f-108">Класс ServiceDebugBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="4a04f-108">The ServiceDebugBehavior class has the following properties:</span></span>  
  
### <a name="httphelppageenabled"></a><span data-ttu-id="4a04f-109">HttpHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="4a04f-109">HttpHelpPageEnabled</span></span>  
 <span data-ttu-id="4a04f-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="4a04f-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="4a04f-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="4a04f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4a04f-112">Определяет, публикует ли служба свой код WSDL по адресу, определяемому атрибутом `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="4a04f-112">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httphelppageurl"></a><span data-ttu-id="4a04f-113">HttpHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="4a04f-113">HttpHelpPageUrl</span></span>  
 <span data-ttu-id="4a04f-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="4a04f-114">Data type: string</span></span>  
  
 <span data-ttu-id="4a04f-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="4a04f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4a04f-116">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTP.</span><span class="sxs-lookup"><span data-stu-id="4a04f-116">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpshelppageenabled"></a><span data-ttu-id="4a04f-117">HttpsHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="4a04f-117">HttpsHelpPageEnabled</span></span>  
 <span data-ttu-id="4a04f-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="4a04f-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="4a04f-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="4a04f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4a04f-120">Определяет, публикует ли служба свой язык WSDL через HTTPS по адресу, указанному в атрибуте `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="4a04f-120">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpshelppageurl"></a><span data-ttu-id="4a04f-121">HttpsHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="4a04f-121">HttpsHelpPageUrl</span></span>  
 <span data-ttu-id="4a04f-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="4a04f-122">Data type: string</span></span>  
  
 <span data-ttu-id="4a04f-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="4a04f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4a04f-124">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4a04f-124">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="4a04f-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="4a04f-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="4a04f-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="4a04f-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="4a04f-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="4a04f-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4a04f-128">Указывает, включать ли информацию об управляемых исключениях в сведения об ошибках SOAP, возвращаемые клиентам для отладки.</span><span class="sxs-lookup"><span data-stu-id="4a04f-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a04f-129">Требования</span><span class="sxs-lookup"><span data-stu-id="4a04f-129">Requirements</span></span>  
  
|<span data-ttu-id="4a04f-130">MOF</span><span class="sxs-lookup"><span data-stu-id="4a04f-130">MOF</span></span>|<span data-ttu-id="4a04f-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4a04f-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4a04f-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="4a04f-132">Namespace</span></span>|<span data-ttu-id="4a04f-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="4a04f-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4a04f-134">См. также</span><span class="sxs-lookup"><span data-stu-id="4a04f-134">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceDebugBehavior>
