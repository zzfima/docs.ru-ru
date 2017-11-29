---
title: "Практическое руководство. Развертывание приложения интеграции COM+"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e5a0510-db3c-4988-a09c-696285836650
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7d6d9103c2d36de81392858fedc249be9f7ae94f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-deploy-a-com-integration-application"></a>Практическое руководство. Развертывание приложения интеграции COM+
Написанное приложение интеграции COM+ может понадобиться развернуть на другом компьютере. В этом разделе описывается перенос приложения COM+ с одного компьютера на другой.  
  
### <a name="moving-a-com-hosted-integration-app"></a>Перенос размещенного в COM+ приложения интеграции  
  
1.  Убедитесь, что на обоих компьютерах установлена платформа [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
2.  Экспортируйте приложение с компьютера A.  
  
3.  Импортируйте приложение на компьютер B.  
  
4.  Задайте корневую папку приложения. По традиции это %PROGRAMFILES%/ComPlus Applications/{GUID_приложения}.  
  
5.  Скопируйте файлы Application.config и Application.manifest из корневой папки приложения на компьютере A в корневую папку приложения на компьютере B.  
  
6.  Отредактируйте адреса конечных точек службы в файле Application.config на компьютере B так, чтобы они указывали на соответствующий компьютер. Например, измените http://machineA/MyService на http://machineB/MyService.  
  
### <a name="moving-a-web-hosted-integration-application"></a>Перенос размещенного на веб-сервере приложения интеграции  
  
1.  Убедитесь, что на обоих компьютерах установлена платформа [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
2.  Экспортируйте приложение с компьютера A.  
  
3.  Импортируйте приложение на компьютер B.  
  
4.  Создайте виртуальный корневой каталог IIS на компьютере B.  
  
5.  Скопируйте файл .SVC (имя_компонента.svc) и файл Web.config из виртуального корневого каталога на компьютере A в только что созданный виртуальный корневой каталог на компьютере B.  
  
## <a name="see-also"></a>См. также  
 [Интеграция с Обзор приложений COM +](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications-overview.md)  
 [Как: Настройка параметров службы COM +](../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)  
 [Как: средство настройки модели служб COM +](../../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)
