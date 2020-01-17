---
title: Форматы метаданных
ms.date: 03/30/2017
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
ms.openlocfilehash: e7208a8d5fd6d100ac2a2c4fb1369a571c63e7fc
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212174"
---
# <a name="metadata-formats"></a>Форматы метаданных
Windows Communication Foundation (WCF) поддерживает форматы метаданных, приведенные в следующей таблице.  
  
## <a name="metadata-specifications-and-usage"></a>Спецификации и использование метаданных  
  
|Протокол|Спецификация и использование|  
|--------------|-----------------------------|  
|WSDL 1.1|[Язык описания веб-служб (WSDL) 1,1](https://www.w3.org/TR/wsdl/)<br /><br /> Для описания служб WCF использует язык описания веб-служб (WSDL).|  
|схема XML|[XML-схема, часть 2: типы типа «второй выпуск](https://www.w3.org/TR/2004/REC-xmlschema-2-20041028/) » и « [схема XML», часть 1. Вторая выпускная структура](https://www.w3.org/TR/2004/REC-xmlschema-1-20041028/)<br /><br /> WCF использует схему XML для описания типов данных, используемых в сообщениях.|  
|WS Policy|[Политика веб-служб 1,2-Framework (WS-Policy)](https://www.w3.org/Submission/WS-Policy/)<br /><br /> [Политика веб-служб 1,5 — платформа](https://www.w3.org/TR/ws-policy/)<br /><br /> WCF использует спецификации WS-Policy 1,2 или 1,5 с утверждениями, зависящими от домена, для описания требований и возможностей службы.|  
|Вложения WS Policy|[Политика веб-служб 1,2 — вложение (WS-Полициаттачмент)](https://www.w3.org/Submission/WS-PolicyAttachment/)<br /><br /> WCF реализует вложения WS-Policy для присоединения выражений политики в различных областях в WSDL.|  
|WS Metadata Exchange|[Обмен метаданными веб-служб (WS-MetadataExchange) версии 1,1](https://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF реализует WS-MetadataExchange для получения схемы XML, WSDL и WS-Policy.|  
|Привязка WS Addressing для WSDL|[Обращение к веб-службам 1,0 — привязка WSDL](https://www.w3.org/TR/ws-addr-wsdl/)<br /><br /> WCF реализует привязку WS-Addressing для WSDL, чтобы присоединить сведения об адресации в WSDL.|  
  
## <a name="see-also"></a>См. также:

- [Протоколы веб-служб, поддерживаемые предоставляемыми системой привязками](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)
- [WSDL и политика](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)
