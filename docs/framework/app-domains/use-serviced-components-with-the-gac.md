---
title: "Использование обслуживаемых компонентов с глобальным кэшем сборок | Microsoft Docs"
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
- assemblies [.NET Framework], global assembly cache
- GAC (global assembly cache), serviced components
- serviced components, global assembly cache
- global assembly cache, serviced components
ms.assetid: 3423e5d9-234c-4571-8161-e35f6d130128
caps.latest.revision: 8
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b94461096bfcf72d2a7ee8bc8b0847e2f753161b
ms.contentlocale: ru-ru
ms.lasthandoff: 06/02/2017

---
# <a name="using-serviced-components-with-the-global-assembly-cache"></a>Использование обслуживаемых компонентов с глобальным кэшем сборок
Обслуживаемые компоненты (компоненты управляемого кода COM+) следует помещать в глобальный кэш сборок. В некоторых ситуациях среда CLR и службы COM+ могут обрабатывать обслуживаемые компоненты, не входящие в глобальный кэш сборок; в других сценариях это невозможно. Это иллюстрируется в следующих примерах.  
  
-   Для обслуживаемых компонентов в серверном приложении COM+ сборка, содержащая компоненты, должна находиться в глобальном кэше сборок, так как Dllhost.exe не может выполняться в том же каталоге, в котором содержатся обслуживаемые компоненты.  
  
-   Для обслуживаемых компонентов в приложении библиотеки COM+ среда выполнения и службы COM+ могут разрешать ссылку на сборку, содержащую компоненты, путем поиска в текущем каталоге. В этом случае сборка может не находиться в глобальном кэше сборок.  
  
-   Ситуация отличается для обслуживаемых компонентов в приложении ASP.NET. Если поместить сборку, содержащую обслуживаемые компоненты, в каталог bin базовой папки приложения и использовать регистрацию по требованию, будет выполняться теневое копирование сборки в кэш загрузки, так как ASP.NET использует возможности теневого копирования среды выполнения.  
  
## <a name="see-also"></a>См. также  
 [Работа со сборками и глобальным кэшем сборок](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)   
 [Gacutil.exe (программа глобального кэша сборок)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
