---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: 2e38eb2c2d42ffc5436562b254a42215ccabbab2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956966"
---
# <a name="servicedebugbehavior"></a><span data-ttu-id="d0afb-102">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="d0afb-102">ServiceDebugBehavior</span></span>
<span data-ttu-id="d0afb-103">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="d0afb-103">ServiceDebugBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0afb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0afb-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="d0afb-105">Методы</span><span class="sxs-lookup"><span data-stu-id="d0afb-105">Methods</span></span>  
 <span data-ttu-id="d0afb-106">Класс ServiceDebugBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="d0afb-106">The ServiceDebugBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d0afb-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="d0afb-107">Properties</span></span>  
 <span data-ttu-id="d0afb-108">Класс ServiceDebugBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="d0afb-108">The ServiceDebugBehavior class has the following properties:</span></span>  
  
### <a name="httphelppageenabled"></a><span data-ttu-id="d0afb-109">HttpHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="d0afb-109">HttpHelpPageEnabled</span></span>  
 <span data-ttu-id="d0afb-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="d0afb-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="d0afb-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="d0afb-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d0afb-112">Определяет, публикует ли служба свой код WSDL по адресу, определяемому атрибутом `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="d0afb-112">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httphelppageurl"></a><span data-ttu-id="d0afb-113">HttpHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="d0afb-113">HttpHelpPageUrl</span></span>  
 <span data-ttu-id="d0afb-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="d0afb-114">Data type: string</span></span>  
  
 <span data-ttu-id="d0afb-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="d0afb-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d0afb-116">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTP.</span><span class="sxs-lookup"><span data-stu-id="d0afb-116">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpshelppageenabled"></a><span data-ttu-id="d0afb-117">HttpsHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="d0afb-117">HttpsHelpPageEnabled</span></span>  
 <span data-ttu-id="d0afb-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="d0afb-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="d0afb-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="d0afb-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d0afb-120">Определяет, публикует ли служба свой язык WSDL через HTTPS по адресу, указанному в атрибуте `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="d0afb-120">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpshelppageurl"></a><span data-ttu-id="d0afb-121">HttpsHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="d0afb-121">HttpsHelpPageUrl</span></span>  
 <span data-ttu-id="d0afb-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="d0afb-122">Data type: string</span></span>  
  
 <span data-ttu-id="d0afb-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="d0afb-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d0afb-124">Задает расположение для публикации языка WSDL службы и его получения с помощью HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d0afb-124">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="d0afb-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="d0afb-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="d0afb-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="d0afb-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="d0afb-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="d0afb-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d0afb-128">Указывает, включать ли информацию об управляемых исключениях в сведения об ошибках SOAP, возвращаемые клиентам для отладки.</span><span class="sxs-lookup"><span data-stu-id="d0afb-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0afb-129">Требования</span><span class="sxs-lookup"><span data-stu-id="d0afb-129">Requirements</span></span>  
  
|<span data-ttu-id="d0afb-130">MOF</span><span class="sxs-lookup"><span data-stu-id="d0afb-130">MOF</span></span>|<span data-ttu-id="d0afb-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d0afb-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d0afb-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="d0afb-132">Namespace</span></span>|<span data-ttu-id="d0afb-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="d0afb-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d0afb-134">См. также</span><span class="sxs-lookup"><span data-stu-id="d0afb-134">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceDebugBehavior>
