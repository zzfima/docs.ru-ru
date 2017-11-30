---
title: XmlDictionaryReaderQuotas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 980a7eacd095dc1b601d63f5a807f2e287c09885
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="4b89d-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="4b89d-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="4b89d-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="4b89d-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b89d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b89d-104">Syntax</span></span>  
  
```  
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4b89d-105">Методы</span><span class="sxs-lookup"><span data-stu-id="4b89d-105">Methods</span></span>  
 <span data-ttu-id="4b89d-106">Класс XmlDictionaryReaderQuotas не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="4b89d-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4b89d-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="4b89d-107">Properties</span></span>  
 <span data-ttu-id="4b89d-108">Класс XmlDictionaryReaderQuotas имеет следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="4b89d-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="4b89d-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="4b89d-109">MaxArrayLength</span></span>  
 <span data-ttu-id="4b89d-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="4b89d-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="4b89d-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="4b89d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b89d-112">Максимально допустимая длина массива.</span><span class="sxs-lookup"><span data-stu-id="4b89d-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="4b89d-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="4b89d-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="4b89d-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="4b89d-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="4b89d-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="4b89d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b89d-116">Максимально допустимое число байтов, возвращаемых для каждой операции чтения.</span><span class="sxs-lookup"><span data-stu-id="4b89d-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="4b89d-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="4b89d-117">MaxDepth</span></span>  
 <span data-ttu-id="4b89d-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="4b89d-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="4b89d-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="4b89d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b89d-120">Максимальная глубина вложенного узла для каждого чтения.</span><span class="sxs-lookup"><span data-stu-id="4b89d-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="4b89d-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="4b89d-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="4b89d-122">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="4b89d-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="4b89d-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="4b89d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b89d-124">Максимально допустимое количество символов в имени таблицы.</span><span class="sxs-lookup"><span data-stu-id="4b89d-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="4b89d-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="4b89d-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="4b89d-126">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="4b89d-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="4b89d-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="4b89d-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4b89d-128">Максимальное допустимое число символов в содержимом элемента XML.</span><span class="sxs-lookup"><span data-stu-id="4b89d-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b89d-129">Требования</span><span class="sxs-lookup"><span data-stu-id="4b89d-129">Requirements</span></span>  
  
|<span data-ttu-id="4b89d-130">MOF</span><span class="sxs-lookup"><span data-stu-id="4b89d-130">MOF</span></span>|<span data-ttu-id="4b89d-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4b89d-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4b89d-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="4b89d-132">Namespace</span></span>|<span data-ttu-id="4b89d-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="4b89d-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4b89d-134">См. также</span><span class="sxs-lookup"><span data-stu-id="4b89d-134">See Also</span></span>  
 <xref:System.Xml.XmlDictionaryReaderQuotas>  
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
