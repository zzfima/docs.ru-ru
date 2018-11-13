---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: 9bc519509b00383be333ac605688950d2709117c
ms.sourcegitcommit: 4bca8f7e172fd019ef437a4803bf5895c6bc4781
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2018
ms.locfileid: "50980535"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="49862-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="49862-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="49862-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="49862-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49862-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49862-104">Syntax</span></span>  
  
```csharp
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="49862-105">Методы</span><span class="sxs-lookup"><span data-stu-id="49862-105">Methods</span></span>  
 <span data-ttu-id="49862-106">Класс XmlDictionaryReaderQuotas не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="49862-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="49862-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="49862-107">Properties</span></span>  
 <span data-ttu-id="49862-108">Класс XmlDictionaryReaderQuotas имеет следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="49862-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="49862-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="49862-109">MaxArrayLength</span></span>  
 <span data-ttu-id="49862-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="49862-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="49862-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="49862-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="49862-112">Максимально допустимая длина массива.</span><span class="sxs-lookup"><span data-stu-id="49862-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="49862-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="49862-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="49862-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="49862-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="49862-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="49862-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="49862-116">Максимально допустимое число байтов, возвращаемых для каждой операции чтения.</span><span class="sxs-lookup"><span data-stu-id="49862-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="49862-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="49862-117">MaxDepth</span></span>  
 <span data-ttu-id="49862-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="49862-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="49862-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="49862-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="49862-120">Максимальная глубина вложенного узла для каждого чтения.</span><span class="sxs-lookup"><span data-stu-id="49862-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="49862-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="49862-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="49862-122">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="49862-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="49862-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="49862-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="49862-124">Максимально допустимое количество символов в имени таблицы.</span><span class="sxs-lookup"><span data-stu-id="49862-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="49862-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="49862-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="49862-126">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="49862-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="49862-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="49862-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="49862-128">Максимальное допустимое число символов в содержимом элемента XML.</span><span class="sxs-lookup"><span data-stu-id="49862-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49862-129">Требования</span><span class="sxs-lookup"><span data-stu-id="49862-129">Requirements</span></span>  
  
|<span data-ttu-id="49862-130">MOF</span><span class="sxs-lookup"><span data-stu-id="49862-130">MOF</span></span>|<span data-ttu-id="49862-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="49862-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="49862-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="49862-132">Namespace</span></span>|<span data-ttu-id="49862-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="49862-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="49862-134">См. также</span><span class="sxs-lookup"><span data-stu-id="49862-134">See Also</span></span>  
 <xref:System.Xml.XmlDictionaryReaderQuotas>  
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
