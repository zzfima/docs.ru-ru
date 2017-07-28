---
title: "Практическое руководство. Использование программы Svcutil.exe для проверки скомпилированного кода службы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Практическое руководство. Использование программы Svcutil.exe для проверки скомпилированного кода службы
Чтобы найти ошибки в реализациях службы и конфигурациях, не размещая службу, можно использовать средство [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
### Проверка службы  
  
1.  Скомпилируйте службу в исполняемый файл и одну или более зависимых сборок.  
  
2.  Откройте окно командной строки SDK.  
  
3.  Из командной строки запустите средство Svcutil.exe, используя следующий формат.  Дополнительные сведения о различных параметрах см. в подразделе «Проверка службы» раздела [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
    ```  
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     Чтобы указать имя конфигурации службы для проверки, необходимо использовать параметр `/serviceName`.  
  
     Аргумент `assemblyPath` задает путь к исполняемому файлу для службы и одной или более сборок, которые содержат типы службы для проверки.  Исполняемая сборка должна содержать связанный файл конфигурации для предоставления конфигурации службы.  Для предоставления нескольких сборок можно использовать стандартные подстановочные знаки командной строки.  
  
## Пример  
 Следующая команда проверяет службу myServiceName, реализованную в исполняемом файле myServiceHost.exe.  Автоматически загружается файл конфигурации для этой службы \(myServiceHost.exe.config\).  
  
```  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## См. также  
 [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)