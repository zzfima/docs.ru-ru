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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 06c0ff11752ae1030e574182cfb825fb87ddc8c7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="3fd86-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="3fd86-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="3fd86-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="3fd86-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fd86-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3fd86-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="3fd86-105">Методы</span><span class="sxs-lookup"><span data-stu-id="3fd86-105">Methods</span></span>  
 <span data-ttu-id="3fd86-106">Класс XmlDictionaryReaderQuotas не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="3fd86-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3fd86-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="3fd86-107">Properties</span></span>  
 <span data-ttu-id="3fd86-108">Класс XmlDictionaryReaderQuotas имеет следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="3fd86-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="3fd86-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="3fd86-109">MaxArrayLength</span></span>  
 <span data-ttu-id="3fd86-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="3fd86-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="3fd86-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="3fd86-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3fd86-112">Максимально допустимая длина массива.</span><span class="sxs-lookup"><span data-stu-id="3fd86-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="3fd86-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="3fd86-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="3fd86-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="3fd86-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="3fd86-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="3fd86-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3fd86-116">Максимально допустимое число байтов, возвращаемых для каждой операции чтения.</span><span class="sxs-lookup"><span data-stu-id="3fd86-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="3fd86-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="3fd86-117">MaxDepth</span></span>  
 <span data-ttu-id="3fd86-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="3fd86-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="3fd86-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="3fd86-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3fd86-120">Максимальная глубина вложенного узла для каждого чтения.</span><span class="sxs-lookup"><span data-stu-id="3fd86-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="3fd86-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="3fd86-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="3fd86-122">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="3fd86-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="3fd86-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="3fd86-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3fd86-124">Максимально допустимое количество символов в имени таблицы.</span><span class="sxs-lookup"><span data-stu-id="3fd86-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="3fd86-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="3fd86-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="3fd86-126">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="3fd86-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="3fd86-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="3fd86-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3fd86-128">Максимальное допустимое число символов в содержимом элемента XML.</span><span class="sxs-lookup"><span data-stu-id="3fd86-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fd86-129">Требования</span><span class="sxs-lookup"><span data-stu-id="3fd86-129">Requirements</span></span>  
  
|<span data-ttu-id="3fd86-130">MOF</span><span class="sxs-lookup"><span data-stu-id="3fd86-130">MOF</span></span>|<span data-ttu-id="3fd86-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="3fd86-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3fd86-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="3fd86-132">Namespace</span></span>|<span data-ttu-id="3fd86-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="3fd86-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3fd86-134">См. также</span><span class="sxs-lookup"><span data-stu-id="3fd86-134">See Also</span></span>  
 <xref:System.Xml.XmlDictionaryReaderQuotas>  
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
