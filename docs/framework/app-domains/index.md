---
title: Программирование с использованием доменов приложений и сборок
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
- application domains, programming
- programming application domains
ms.assetid: 96d3b8e3-bef8-4da0-9a81-9841e23a94e9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7124b6b234601e3afc27109ac318f47e3fe40c35
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675355"
---
# <a name="programming-with-application-domains-and-assemblies"></a>Программирование с использованием доменов приложений и сборок
Такие узлы, как Microsoft Internet Explorer, ASP.NET и оболочки Windows, загружают среду CLR в процесс, создают в этом процессе [домен приложения](../../../docs/framework/app-domains/application-domains.md), а затем загружают и выполняют пользовательский код в этом домене приложения при запуске приложения .NET Framework. В большинстве случаев вам не нужно беспокоиться о создании доменов приложений и загрузке сборок в них, так как эти задачи выполняет хост-приложение среды выполнения.  
  
 Тем не менее, если вы создаете приложение для размещения среды CLR, средства или код для создания средств или код для выгрузки программным способом, а также подключаемые компоненты для динамической выгрузки и повторной загрузки, вы будете создавать домены приложений. Даже если вы не создаете хост-приложение среды выполнения, в этом разделе содержатся важные сведения по работе с доменами приложений и загруженными в них сборками.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Руководства по работе с доменами приложений и сборками](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)  
 Ссылки на все разделы практического руководства базовой документации по программированию с использованием доменов приложений и сборок.  
  
 [Использование доменов приложений](../../../docs/framework/app-domains/use.md)  
 Примеры создания, настройки и использования доменов приложений.  
  
 [Программирование с использованием сборок](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 Описание способов создания, подписи и установки атрибутов сборок.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Предоставление динамических методов и сборок](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 Описание способов создания динамических сборок.  
  
 [Сборки в среде CLR](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 Общие сведения о сборках.  
  
 [Домены приложений](../../../docs/framework/app-domains/application-domains.md)  
 Общие сведения о доменах приложений.  
  
 [Общие сведения о классе Reflection](../../../docs/framework/reflection-and-codedom/reflection.md)  
 Использование класса **Reflection** для получения сведений о сборке.
