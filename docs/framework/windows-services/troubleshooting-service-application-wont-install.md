---
title: "Устранение неполадок: Реализовано службы приложения &#39; Установка t"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 43c973d83d2d1b614cf0ce49ba8d4af24123b47e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="troubleshooting-service-application-won39t-install"></a>Устранение неполадок: Реализовано службы приложения &#39; Установка t
Если приложение службы не устанавливается правильно, проверьте, убедитесь, что <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> свойства для класса службы имеет значение то же значение, как показано в программе установки для этой службы. Значение должно быть одинаковым в обоих случаях для правильной установки службы.  
  
> [!NOTE]
>  Можно также найти журналы установки, чтобы получить отзывы о ходе процесса установки.  
  
 Необходимо также проверить, чтобы убедиться, что другая служба с таким именем уже установлен. Имена служб должны быть уникальными для успешной установки.  
  
## <a name="see-also"></a>См. также  
 [Знакомство с приложениями служб Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
