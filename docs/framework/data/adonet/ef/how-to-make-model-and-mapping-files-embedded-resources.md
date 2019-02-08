---
title: Как выполнить  Модели и сопоставления файлов внедренных ресурсов
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: 7827ecce0fe7f5c21291d3ba2edd925c6a8e5960
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826529"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a>Как выполнить  Модели и сопоставления файлов внедренных ресурсов
[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Позволяет развертывать файлы модели и сопоставления как внедренные ресурсы приложения. Сборка с внедренными файлами моделей и сопоставления должна быть загружена в том же домене приложения, что и соединение сущности. Дополнительные сведения см. в статье [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md) (Строки подключения). По умолчанию средства [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] внедряют файлы модели и сопоставления. При определении файлов модели и сопоставления вручную следует использовать данную процедуру для обеспечения того, чтобы файлы были развернуты как внедренные ресурсы совместно с приложением [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
> [!NOTE]
>  Чтобы обеспечить поддержку внедренных ресурсов, необходимо повторить эту процедуру после каждого изменения файлов модели и сопоставления.  
  
### <a name="to-embed-model-and-mapping-files"></a>Внедрение файлов модели и сопоставления  
  
1.  В **обозревателе решений**, выберите файл концептуальной (CSDL).  
  
2.  В **свойства** установите **действие при построении** для **внедренный ресурс**.  
  
3.  Повторите шаги 1 и 2 для файла хранения с расширением SSDL и файла сопоставления с расширением MSL.  
  
4.  В **обозревателе решений**, дважды щелкните файл App.config, а затем измените `Metadata` параметр в `connectionString` атрибут на основе одного из следующих форматов:  
  
    -   `Metadata=` `res://<assemblyFullName>/<resourceName>;`  
  
    -   `Metadata=` `res://*/<resourceName>;`  
  
    -   `Metadata=res://*;`  
  
     Дополнительные сведения см. в статье [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md) (Строки подключения).  
  
## <a name="example"></a>Пример  
 Следующая строка подключения ссылается на внедренные файлы модели и сопоставления для [модели AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks). Эта строка соединения хранится в файле App.config проекта.  
  
  
  
## <a name="see-also"></a>См. также
- [Моделирование и сопоставление](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [Практическое руководство. Определение строки подключения](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)
- [Практическое руководство. Построить строку соединения EntityConnection](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)
- [Средства модели EDM ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
