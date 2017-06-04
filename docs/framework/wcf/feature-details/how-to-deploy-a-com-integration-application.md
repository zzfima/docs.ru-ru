---
title: "Как развертывать приложения интеграции COM+ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2e5a0510-db3c-4988-a09c-696285836650
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Как развертывать приложения интеграции COM+
Написанное приложение интеграции COM\+ может понадобиться развернуть на другом компьютере.В этом разделе описывается перенос приложения COM\+ с одного компьютера на другой.  
  
### Перенос размещенного в COM\+ приложения интеграции  
  
1.  Убедитесь, что на обоих компьютерах установлена платформа [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
2.  Экспортируйте приложение с компьютера A.  
  
3.  Импортируйте приложение на компьютер B.  
  
4.  Задайте корневую папку приложения.По традиции это %PROGRAMFILES%\/ComPlus Applications\/{GUID\_приложения}.  
  
5.  Скопируйте файлы Application.config и Application.manifest из корневой папки приложения на компьютере A в корневую папку приложения на компьютере B.  
  
6.  Отредактируйте адреса конечных точек службы в файле Application.config на компьютере B так, чтобы они указывали на соответствующий компьютер.Например, измените http:\/\/machineA\/MyService на http:\/\/machineB\/MyService.  
  
### Перенос размещенного на веб\-сервере приложения интеграции  
  
1.  Убедитесь, что на обоих компьютерах установлена платформа [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
2.  Экспортируйте приложение с компьютера A.  
  
3.  Импортируйте приложение на компьютер B.  
  
4.  Создайте виртуальный корневой каталог IIS на компьютере B.  
  
5.  Скопируйте файл .SVC \(имя\_компонента.svc\) и файл Web.config из виртуального корневого каталога на компьютере A в только что созданный виртуальный корневой каталог на компьютере B.  
  
## См. также  
 [Общие сведения об интеграции с приложениями COM\+](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications-overview.md)   
 [Практическое руководство. Настройка параметров службы COM\+](../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)   
 [Как использовать программу командной строки настройки модели служб COM\+](../../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)