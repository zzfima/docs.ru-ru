---
title: "Форматы метаданных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ee7376f87fd0e4ce15d192dd53f872e84187acc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="metadata-formats"></a><span data-ttu-id="09334-102">Форматы метаданных</span><span class="sxs-lookup"><span data-stu-id="09334-102">Metadata Formats</span></span>
<span data-ttu-id="09334-103">В следующей таблице перечислены форматы метаданных, поддерживаемые [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09334-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] supports the metadata formats in the following table.</span></span>  
  
## <a name="metadata-specifications-and-usage"></a><span data-ttu-id="09334-104">Спецификации и использование метаданных</span><span class="sxs-lookup"><span data-stu-id="09334-104">Metadata Specifications and Usage</span></span>  
  
|<span data-ttu-id="09334-105">Протокол</span><span class="sxs-lookup"><span data-stu-id="09334-105">Protocol</span></span>|<span data-ttu-id="09334-106">Спецификация и использование</span><span class="sxs-lookup"><span data-stu-id="09334-106">Specification and usage</span></span>|  
|--------------|-----------------------------|  
|<span data-ttu-id="09334-107">WSDL 1.1</span><span class="sxs-lookup"><span data-stu-id="09334-107">WSDL 1.1</span></span>|[<span data-ttu-id="09334-108">Язык описания веб-служб (WSDL) 1.1</span><span class="sxs-lookup"><span data-stu-id="09334-108">Web Services Description Language (WSDL) 1.1</span></span>](http://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> <span data-ttu-id="09334-109">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] язык WSDL используется для описания служб.</span><span class="sxs-lookup"><span data-stu-id="09334-109">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses Web Services Description Language (WSDL) to describe services.</span></span>|  
|<span data-ttu-id="09334-110">схема XML</span><span class="sxs-lookup"><span data-stu-id="09334-110">XML Schema</span></span>|<span data-ttu-id="09334-111">[Схема XML, часть 2: Datatypes Second Edition](http://go.microsoft.com/fwlink/?LinkId=94861) и [XML Schema Part 1: Structures Second Edition](http://go.microsoft.com/fwlink/?LinkId=94862)</span><span class="sxs-lookup"><span data-stu-id="09334-111">[XML Schema Part 2: Datatypes Second Edition](http://go.microsoft.com/fwlink/?LinkId=94861) and [XML Schema Part 1: Structures Second Edition](http://go.microsoft.com/fwlink/?LinkId=94862)</span></span><br /><br /> <span data-ttu-id="09334-112">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] схема XML используется для описания типов данных, используемых в сообщениях.</span><span class="sxs-lookup"><span data-stu-id="09334-112">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses the XML Schema to describe data types used in messages.</span></span>|  
|<span data-ttu-id="09334-113">WS Policy</span><span class="sxs-lookup"><span data-stu-id="09334-113">WS Policy</span></span>|[<span data-ttu-id="09334-114">Политика веб служб 1.2 — платформа (WS-Policy)</span><span class="sxs-lookup"><span data-stu-id="09334-114">Web Services Policy 1.2 - Framework (WS-Policy)</span></span>](http://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> [<span data-ttu-id="09334-115">Политика веб служб 1.5 — платформа</span><span class="sxs-lookup"><span data-stu-id="09334-115">Web Services Policy 1.5 - Framework</span></span>](http://go.microsoft.com/fwlink/?LinkId=94865)<br /><br /> <span data-ttu-id="09334-116">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] спецификации WS-Policy 1.2 или 1.5 используются вместе с доменными утверждениями для описания требований и возможностей служб.</span><span class="sxs-lookup"><span data-stu-id="09334-116">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses the WS-Policy 1.2 or 1.5 specifications with domain-specific assertions to describe service requirements and capabilities.</span></span>|  
|<span data-ttu-id="09334-117">Вложения WS Policy</span><span class="sxs-lookup"><span data-stu-id="09334-117">WS Policy Attachments</span></span>|[<span data-ttu-id="09334-118">Политика веб служб 1.2 — вложение (WS-PolicyAttachment)</span><span class="sxs-lookup"><span data-stu-id="09334-118">Web Services Policy 1.2 - Attachment (WS-PolicyAttachment)</span></span>](http://go.microsoft.com/fwlink/?LinkId=94866)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="09334-119"> реализует спецификацию вложений WS-Policy для прикрепления выражений политики в различных областях на языке WSDL.</span><span class="sxs-lookup"><span data-stu-id="09334-119"> implements WS-Policy Attachments to attach policy expressions at various scopes in WSDL.</span></span>|  
|<span data-ttu-id="09334-120">WS Metadata Exchange</span><span class="sxs-lookup"><span data-stu-id="09334-120">WS Metadata Exchange</span></span>|[<span data-ttu-id="09334-121">Обмен метаданными веб служб (WS-MetadataExchange) версии 1.1</span><span class="sxs-lookup"><span data-stu-id="09334-121">Web Services Metadata Exchange (WS-MetadataExchange) version 1.1</span></span>](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="09334-122"> реализует спецификацию WS-MetadataExchange для извлечения схемы XML, языка WSDL и спецификации WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="09334-122"> implements WS-MetadataExchange to retrieve XML Schema, WSDL, and WS-Policy.</span></span>|  
|<span data-ttu-id="09334-123">Привязка WS Addressing для WSDL</span><span class="sxs-lookup"><span data-stu-id="09334-123">WS Addressing Binding for WSDL</span></span>|[<span data-ttu-id="09334-124">Web Services Addressing 1.0 - привязка WSDL</span><span class="sxs-lookup"><span data-stu-id="09334-124">Web Services Addressing 1.0 - WSDL Binding</span></span>](http://go.microsoft.com/fwlink/?LinkId=94869)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="09334-125"> реализует спецификацию привязки WS-Addressing для WSDL для вложения сведений об адресации в WSDL.</span><span class="sxs-lookup"><span data-stu-id="09334-125"> implements WS-Addressing Binding for WSDL to attach addressing information in WSDL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="09334-126">См. также</span><span class="sxs-lookup"><span data-stu-id="09334-126">See Also</span></span>  
 [<span data-ttu-id="09334-127">Протоколы, поддерживаемые предоставляемыми системой привязками веб-служб</span><span class="sxs-lookup"><span data-stu-id="09334-127">Web Services Protocols Supported by System-Provided Interoperability Bindings</span></span>](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
 [<span data-ttu-id="09334-128">WSDL и политика</span><span class="sxs-lookup"><span data-stu-id="09334-128">WSDL and Policy</span></span>](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)
