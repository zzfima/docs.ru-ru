---
title: 'Устранение неполадок: невозможно установить приложение-службу'
ms.date: 03/30/2017
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
author: ghogen
manager: douge
ms.openlocfilehash: 1f3e5674f9a52627efdc24d6c70c0ab16dcdbbbd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509664"
---
# <a name="troubleshooting-service-application-won39t-install"></a>Устранение неполадок: невозможно установить приложение-службу
Если приложение-служба не устанавливается надлежащим образом, убедитесь, что для свойства <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> класса службы задано значение, которое отображается в установщике этой службы. Для правильной установки службы необходимо, чтобы эти значения совпадали.  
  
> [!NOTE]
>  Сведения о ходе установки также можно найти в журналах установки.  
  
 Также убедитесь, что у вас не установлена другая служба с таким же именем. Для успешной установки необходимо, чтобы у каждой службы было уникальное имя.  
  
## <a name="see-also"></a>См. также  
 [Знакомство с приложениями служб Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
