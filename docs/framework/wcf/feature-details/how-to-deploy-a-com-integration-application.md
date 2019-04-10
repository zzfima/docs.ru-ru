---
title: Практическое руководство. Развертывание приложения интеграции COM+
ms.date: 03/30/2017
ms.assetid: 2e5a0510-db3c-4988-a09c-696285836650
ms.openlocfilehash: fcf525943e6e453253c6f4d3bcfa8a1a08df6909
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343386"
---
# <a name="how-to-deploy-a-com-integration-application"></a>Практическое руководство. Развертывание приложения интеграции COM+
Написанное приложение интеграции COM+ может понадобиться развернуть на другом компьютере. В этом разделе описывается перенос приложения COM+ с одного компьютера на другой.  
  
### <a name="moving-a-com-hosted-integration-app"></a>Перенос размещенного в COM+ приложения интеграции  
  
1. Убедитесь, что на обоих компьютерах установлен продукт WCF.  
  
2. Экспортируйте приложение с компьютера A.  
  
3. Импортируйте приложение на компьютер B.  
  
4. Задайте корневую папку приложения. По традиции это %PROGRAMFILES%/ComPlus Applications/{GUID_приложения}.  
  
5. Скопируйте файлы Application.config и Application.manifest из корневой папки приложения на компьютере A в корневую папку приложения на компьютере B.  
  
6. Отредактируйте адреса конечных точек службы в файле Application.config на компьютере B так, чтобы они указывали на соответствующий компьютер. Например, измените `http://machineA/MyService` на `http://machineB/MyService`.  
  
### <a name="moving-a-web-hosted-integration-application"></a>Перенос размещенного на веб-сервере приложения интеграции  
  
1. Убедитесь, что на обоих компьютерах установлен продукт WCF.  
  
2. Экспортируйте приложение с компьютера A.  
  
3. Импортируйте приложение на компьютер B.  
  
4. Создайте виртуальный корневой каталог IIS на компьютере B.  
  
5. Скопируйте файл .SVC (имя_компонента.svc) и файл Web.config из виртуального корневого каталога на компьютере A в только что созданный виртуальный корневой каталог на компьютере B.  
  
## <a name="see-also"></a>См. также

- [Общие сведения об интеграции с приложениями COM+](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications-overview.md)
- [Практическое руководство. Настройка параметров службы COM+](../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
- [Практическое руководство. Использование программы командной строки настройки модели служб COM+](../../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)
