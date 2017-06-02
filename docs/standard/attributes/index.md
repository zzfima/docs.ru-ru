---
title: "Расширение метаданных с помощью атрибутов | Документация Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- metadata, extending
- attributes [.NET Framework], metadata
- elements [.NET Framework], attributes
- common language runtime, attributes
- annotating programming elements
- keyword-like descriptive declarations
- runtime, attributes
- extending metadata
ms.assetid: 30386922-1e00-4602-9ebf-526b271a8b87
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 10ad4fe315283bfc76b24de537574ee8ef2ba979
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="extending-metadata-using-attributes"></a>Расширение метаданных с помощью атрибутов
Среда CLR позволяет добавлять описательные объявления со свойствами ключевого слова, называемые атрибутами, для комментирования элементов программирования, таких как типы, поля, методы и свойства. При компиляции кода для среды выполнения он преобразуется в MSIL-код и вместе с метаданными, создаваемыми компилятором, помещается в переносимый исполняемый файл (PE). Атрибуты позволяют поместить в метаданные дополнительные описательные сведения, которые можно извлечь с помощью служб отражения среды выполнения. Компилятор создает атрибуты при объявлении экземпляров специальных классов, производных от <xref:System.Attribute?displayProperty=fullName>.  
  
 Платформа .NET Framework использует атрибуты по ряду причин и для решения ряда проблем. Атрибуты описывают, каким образом следует сериализовать данные, задают характеристики, используемые для усиления безопасности, и ограничивают оптимизацию JIT-компилятором, благодаря чему возможна простая отладка кода. В атрибутах также может записываться имя файла или автор кода, или же они могут управлять видимостью элементов управления и членов при разработке форм.  
  
## <a name="related-topics"></a>См. также  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Применение атрибутов](../../../docs/standard/attributes/applying-attributes.md)|Описание порядка применения атрибута к элементу кода.|  
|[Написание настраиваемых атрибутов](../../../docs/standard/attributes/writing-custom-attributes.md)|Описание разработки пользовательских классов атрибутов.|  
|[Извлечение информации, сохраненной в атрибуте](../../../docs/standard/attributes/retrieving-information-stored-in-attributes.md)|Описание порядка получения настраиваемых атрибутов для кода, загруженного в контекст выполнения.|  
|[Метаданные и компоненты с самоописанием](../../../docs/standard/metadata-and-self-describing-components.md)|Общие сведения о метаданных и описание их реализации в переносимом исполняемом файле (PE) платформы .NET Framework.|  
|[Практическое руководство. Загрузка сборок в контекст, предназначенный только для отражения](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)|Описание способов получения сведений настраиваемых атрибутов в контексте, предназначенном только для отражения.|  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Attribute?displayProperty=fullName>
