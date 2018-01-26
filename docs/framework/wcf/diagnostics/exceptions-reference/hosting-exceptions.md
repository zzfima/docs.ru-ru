---
title: "Исключения размещения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad9e14f8-fa17-4d59-b365-fe0e7ec17c98
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b296578efb6eb9b1e6372dbad647fdea22dbaddf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="hosting-exceptions"></a>Исключения размещения
В этом разделе перечислены все исключения, создаваемые Hosting.  
  
## <a name="exception-list"></a>Список исключений  
  
|Код ресурса|Строка ресурса|  
|-------------------|---------------------|  
|Hosting_AddressIsAbsoluteUri|Полный универсальный код ресурса (URI) не допускается. Интерфейс API ServiceHostingEnvironment.EnsureServiceAvailable не допускает использования полных URI. Используйте виртуальный путь для соответствующей службы.|  
|Hosting_BuildProviderCouldNotCreateType|Не удалось загрузить указанный тип CLR во время компиляции службы. Убедитесь, что этот тип определяется либо в исходном файле, расположенном в приложения \\каталоге \App_Code, содержащихся в скомпилированной сборке найдены в тестируемом приложении \\\bin каталога или присутствует в сборке, установленной в Глобальный кэш сборок. Имя типа вводится с учетом регистра. Каталоги, такие как \\\App_Code и \\\bin должен быть расположен в корневом каталоге приложения. \\\App_Code и \\\bin не могут быть вложены в подкаталоги.|
