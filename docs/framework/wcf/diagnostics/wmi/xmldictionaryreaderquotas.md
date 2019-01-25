---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: f24865fb0affa7b4516a14fc05b905995826e82e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597675"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="00223-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="00223-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="00223-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="00223-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00223-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00223-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="00223-105">Методы</span><span class="sxs-lookup"><span data-stu-id="00223-105">Methods</span></span>  
 <span data-ttu-id="00223-106">Класс XmlDictionaryReaderQuotas не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="00223-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="00223-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="00223-107">Properties</span></span>  
 <span data-ttu-id="00223-108">Класс XmlDictionaryReaderQuotas имеет следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="00223-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="00223-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="00223-109">MaxArrayLength</span></span>  
 <span data-ttu-id="00223-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="00223-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="00223-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="00223-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="00223-112">Максимально допустимая длина массива.</span><span class="sxs-lookup"><span data-stu-id="00223-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="00223-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="00223-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="00223-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="00223-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="00223-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="00223-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="00223-116">Максимально допустимое число байтов, возвращаемых для каждой операции чтения.</span><span class="sxs-lookup"><span data-stu-id="00223-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="00223-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="00223-117">MaxDepth</span></span>  
 <span data-ttu-id="00223-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="00223-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="00223-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="00223-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="00223-120">Максимальная глубина вложенного узла для каждого чтения.</span><span class="sxs-lookup"><span data-stu-id="00223-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="00223-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="00223-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="00223-122">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="00223-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="00223-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="00223-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="00223-124">Максимально допустимое количество символов в имени таблицы.</span><span class="sxs-lookup"><span data-stu-id="00223-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="00223-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="00223-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="00223-126">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="00223-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="00223-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="00223-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="00223-128">Максимальное допустимое число символов в содержимом элемента XML.</span><span class="sxs-lookup"><span data-stu-id="00223-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00223-129">Требования</span><span class="sxs-lookup"><span data-stu-id="00223-129">Requirements</span></span>  
  
|<span data-ttu-id="00223-130">MOF</span><span class="sxs-lookup"><span data-stu-id="00223-130">MOF</span></span>|<span data-ttu-id="00223-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="00223-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="00223-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="00223-132">Namespace</span></span>|<span data-ttu-id="00223-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="00223-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="00223-134">См. также</span><span class="sxs-lookup"><span data-stu-id="00223-134">See also</span></span>
- <xref:System.Xml.XmlDictionaryReaderQuotas>
- <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
