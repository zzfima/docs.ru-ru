---
title: "Практическое руководство. Создание встроенных ресурсов файлов модели и сопоставления"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 6b8439e81c9a77f15556c21c5e96add86265c4ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a>Практическое руководство. Создание встроенных ресурсов файлов модели и сопоставления
[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Позволяет развертывать файлы модели и сопоставления как внедренные ресурсы приложения. Сборка с внедренными файлами моделей и сопоставления должна быть загружена в том же домене приложения, что и соединение сущности. Дополнительные сведения см. в статье [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md) (Строки подключения). По умолчанию средства [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] внедряют файлы модели и сопоставления. При определении файлов модели и сопоставления вручную следует использовать данную процедуру для обеспечения того, чтобы файлы были развернуты как внедренные ресурсы совместно с приложением [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
> [!NOTE]
>  Чтобы обеспечить поддержку внедренных ресурсов, необходимо повторить эту процедуру после каждого изменения файлов модели и сопоставления.  
  
### <a name="to-embed-model-and-mapping-files"></a>Внедрение файлов модели и сопоставления  
  
1.  В **обозревателе решений**, выберите файл концептуальной (CSDL).  
  
2.  В **свойства** задайте **действие при построении** для **внедренный ресурс**.  
  
3.  Повторите шаги 1 и 2 для файла хранения с расширением SSDL и файла сопоставления с расширением MSL.  
  
4.  В **обозревателе решений**, дважды щелкните файл App.config и затем изменить `Metadata` параметр в `connectionString` атрибут на основе одного из следующих форматов:  
  
    -   `Metadata=` `res://<assemblyFullName>/<resourceName>;`  
  
    -   `Metadata=` `res://*/<resourceName>;`  
  
    -   `Metadata=res://*;`  
  
     Дополнительные сведения см. в статье [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md) (Строки подключения).  
  
## <a name="example"></a>Пример  
 Следующая строка подключения ссылается на внедренные файлы модели и сопоставления для [модели AdventureWorks Sales](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832). Эта строка соединения хранится в файле App.config проекта.  
  
  
  
## <a name="see-also"></a>См. также  
 [Моделирование и сопоставление](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [Практическое руководство. Определение строки подключения](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)  
 [Практическое руководство. Сборка строки подключения EntityConnection](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
 [Средства работы с моделью EDM ADO.NET](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)
