---
title: "Расположение сборки | Документы Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4ee16bb622b03a5c9975a896aab951ae74d184a9
ms.contentlocale: ru-ru
ms.lasthandoff: 06/02/2017

---
# <a name="assembly-location"></a>Расположение сборки
От места расположения сборки зависит, сможет ли среда CLR найти сборку по ссылке на нее. Это расположение также определяет возможность совместного использования сборки вместе с другими сборками. Для развертывания сборки можно использовать следующие расположения.  
  
-   Каталог приложения или его подкаталоги  
  
     Это наиболее часто используемое место развертывания сборок. Структура подкаталогов корневого каталога приложения может зависеть от языка или региональных параметров. Если в атрибутах сборки также задан язык и региональные параметры, то она должна располагаться в подкаталоге каталога приложения, название которого соответствует этому языку и региональным параметрам.  
  
-   Глобальный кэш сборок.  
  
     Это кэш кода уровня компьютера, который имеется на любом компьютере с установленной средой CLR. В большинстве случаев при необходимости совместного использования сборки в нескольких приложениях ее следует расположить в глобальном кэше сборок.  
  
-   На HTTP-сервере.  
  
     Сборка, развернутая на HTTP-сервере, должна иметь строгое имя; в разделе базы кода файла конфигурации приложения должно присутствовать указание на сборку.  
  
## <a name="see-also"></a>См. также  
 [Создание сборок](../../../docs/framework/app-domains/create-assemblies.md)   
 [Глобальный кэш сборок](../../../docs/framework/app-domains/gac.md)   
 [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [Программирование с использованием сборок](../../../docs/framework/app-domains/programming-with-assemblies.md)
