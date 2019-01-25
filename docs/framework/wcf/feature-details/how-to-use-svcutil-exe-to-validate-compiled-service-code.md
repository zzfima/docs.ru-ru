---
title: Как выполнить Использовать Svcutil.exe для проверки скомпилированного кода службы
ms.date: 03/30/2017
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
ms.openlocfilehash: a06cf57fce883753af4686b294396d6d6da73a13
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54531932"
---
# <a name="how-to-use-svcutilexe-to-validate-compiled-service-code"></a>Как выполнить Использовать Svcutil.exe для проверки скомпилированного кода службы
Можно использовать [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для обнаружения ошибок в реализациях службы и конфигурациях без размещения службы.  
  
### <a name="to-validate-a-service"></a>Проверка службы  
  
1.  Скомпилируйте службу в исполняемый файл и одну или более зависимых сборок.  
  
2.  Откройте окно командной строки SDK.  
  
3.  Из командной строки запустите средство Svcutil.exe, используя следующий формат. Дополнительные сведения о различных параметрах см. в разделе Validationsection службы из [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) раздела.  
  
    ```  
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     Чтобы указать имя конфигурации службы для проверки, необходимо использовать параметр `/serviceName`.  
  
     Аргумент `assemblyPath` задает путь к исполняемому файлу для службы и одной или более сборок, которые содержат типы службы для проверки. Исполняемая сборка должна содержать связанный файл конфигурации для предоставления конфигурации службы. Для предоставления нескольких сборок можно использовать стандартные подстановочные знаки командной строки.  
  
## <a name="example"></a>Пример  
 Следующая команда проверяет службу myServiceName, реализованную в исполняемом файле myServiceHost.exe.  Автоматически загружается файл конфигурации для этой службы (myServiceHost.exe.config).  
  
```  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## <a name="see-also"></a>См. также
- [Служебная программа для метаданных ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
