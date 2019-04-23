---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: f1c12a0a60397a84d4e9ff0241c4182b4511af5c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59767712"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="27a18-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="27a18-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="27a18-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="27a18-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27a18-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27a18-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="27a18-105">Методы</span><span class="sxs-lookup"><span data-stu-id="27a18-105">Methods</span></span>  
 <span data-ttu-id="27a18-106">Класс XmlDictionaryReaderQuotas не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="27a18-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="27a18-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="27a18-107">Properties</span></span>  
 <span data-ttu-id="27a18-108">Класс XmlDictionaryReaderQuotas имеет следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="27a18-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="27a18-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="27a18-109">MaxArrayLength</span></span>  
 <span data-ttu-id="27a18-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="27a18-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="27a18-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="27a18-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="27a18-112">Максимально допустимая длина массива.</span><span class="sxs-lookup"><span data-stu-id="27a18-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="27a18-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="27a18-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="27a18-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="27a18-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="27a18-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="27a18-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="27a18-116">Максимально допустимое число байтов, возвращаемых для каждой операции чтения.</span><span class="sxs-lookup"><span data-stu-id="27a18-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="27a18-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="27a18-117">MaxDepth</span></span>  
 <span data-ttu-id="27a18-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="27a18-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="27a18-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="27a18-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="27a18-120">Максимальная глубина вложенного узла для каждого чтения.</span><span class="sxs-lookup"><span data-stu-id="27a18-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="27a18-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="27a18-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="27a18-122">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="27a18-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="27a18-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="27a18-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="27a18-124">Максимально допустимое количество символов в имени таблицы.</span><span class="sxs-lookup"><span data-stu-id="27a18-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="27a18-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="27a18-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="27a18-126">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="27a18-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="27a18-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="27a18-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="27a18-128">Максимальное допустимое число символов в содержимом элемента XML.</span><span class="sxs-lookup"><span data-stu-id="27a18-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27a18-129">Требования</span><span class="sxs-lookup"><span data-stu-id="27a18-129">Requirements</span></span>  
  
|<span data-ttu-id="27a18-130">MOF</span><span class="sxs-lookup"><span data-stu-id="27a18-130">MOF</span></span>|<span data-ttu-id="27a18-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="27a18-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="27a18-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="27a18-132">Namespace</span></span>|<span data-ttu-id="27a18-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="27a18-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27a18-134">См. также</span><span class="sxs-lookup"><span data-stu-id="27a18-134">See also</span></span>

- <xref:System.Xml.XmlDictionaryReaderQuotas>
- <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
