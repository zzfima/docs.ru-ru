---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: 9bc519509b00383be333ac605688950d2709117c
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50044233"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="a6dbf-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="a6dbf-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="a6dbf-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="a6dbf-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6dbf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6dbf-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="a6dbf-105">Методы</span><span class="sxs-lookup"><span data-stu-id="a6dbf-105">Methods</span></span>  
 <span data-ttu-id="a6dbf-106">Класс XmlDictionaryReaderQuotas не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="a6dbf-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a6dbf-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="a6dbf-107">Properties</span></span>  
 <span data-ttu-id="a6dbf-108">Класс XmlDictionaryReaderQuotas имеет следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="a6dbf-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="a6dbf-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="a6dbf-109">MaxArrayLength</span></span>  
 <span data-ttu-id="a6dbf-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="a6dbf-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="a6dbf-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="a6dbf-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a6dbf-112">Максимально допустимая длина массива.</span><span class="sxs-lookup"><span data-stu-id="a6dbf-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="a6dbf-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="a6dbf-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="a6dbf-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="a6dbf-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="a6dbf-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="a6dbf-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a6dbf-116">Максимально допустимое число байтов, возвращаемых для каждой операции чтения.</span><span class="sxs-lookup"><span data-stu-id="a6dbf-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="a6dbf-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="a6dbf-117">MaxDepth</span></span>  
 <span data-ttu-id="a6dbf-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="a6dbf-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="a6dbf-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="a6dbf-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a6dbf-120">Максимальная глубина вложенного узла для каждого чтения.</span><span class="sxs-lookup"><span data-stu-id="a6dbf-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="a6dbf-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="a6dbf-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="a6dbf-122">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="a6dbf-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="a6dbf-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="a6dbf-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a6dbf-124">Максимально допустимое количество символов в имени таблицы.</span><span class="sxs-lookup"><span data-stu-id="a6dbf-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="a6dbf-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="a6dbf-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="a6dbf-126">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="a6dbf-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="a6dbf-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="a6dbf-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a6dbf-128">Максимальное допустимое число символов в содержимом элемента XML.</span><span class="sxs-lookup"><span data-stu-id="a6dbf-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6dbf-129">Требования</span><span class="sxs-lookup"><span data-stu-id="a6dbf-129">Requirements</span></span>  
  
|<span data-ttu-id="a6dbf-130">MOF</span><span class="sxs-lookup"><span data-stu-id="a6dbf-130">MOF</span></span>|<span data-ttu-id="a6dbf-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a6dbf-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a6dbf-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="a6dbf-132">Namespace</span></span>|<span data-ttu-id="a6dbf-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="a6dbf-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a6dbf-134">См. также</span><span class="sxs-lookup"><span data-stu-id="a6dbf-134">See Also</span></span>  
 <xref:System.Xml.XmlDictionaryReaderQuotas>  
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
