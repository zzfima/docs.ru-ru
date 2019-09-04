---
title: Практическое руководство. Создание встроенных ресурсов файлов модели и сопоставления
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: c88e0c09742d76c7508d7d782eabbe46035d3501
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251446"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a>Практическое руководство. Создание встроенных ресурсов файлов модели и сопоставления
[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Позволяет развертывать файлы модели и сопоставления как внедренные ресурсы приложения. Сборка с внедренными файлами моделей и сопоставления должна быть загружена в том же домене приложения, что и соединение сущности. Дополнительные сведения см. в статье [Connection Strings](connection-strings.md) (Строки подключения). По умолчанию средства EDM внедряют файлы модели и сопоставления. При определении файлов модели и сопоставления вручную следует использовать данную процедуру для обеспечения того, чтобы файлы были развернуты как внедренные ресурсы совместно с приложением [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
> [!NOTE]
> Чтобы обеспечить поддержку внедренных ресурсов, необходимо повторить эту процедуру после каждого изменения файлов модели и сопоставления.  
  
### <a name="to-embed-model-and-mapping-files"></a>Внедрение файлов модели и сопоставления  
  
1. В **Обозреватель решений**выберите концептуальный файл (CSDL).  
  
2. На панели **Свойства** задайте для параметра **действие при сборке** значение **внедренный ресурс**.  
  
3. Повторите шаги 1 и 2 для файла хранения с расширением SSDL и файла сопоставления с расширением MSL.  
  
4. В **Обозреватель решений**дважды щелкните файл App. config, а затем измените `Metadata` параметр в `connectionString` атрибуте на основе одного из следующих форматов:  
  
    - `Metadata=` `res://<assemblyFullName>/<resourceName>;`  
  
    - `Metadata=` `res://*/<resourceName>;`  
  
    - `Metadata=res://*;`  
  
     Дополнительные сведения см. в статье [Connection Strings](connection-strings.md) (Строки подключения).  
  
## <a name="example"></a>Пример  
 Следующая строка подключения ссылается на внедренную модель и файлы сопоставления для [модели AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks). Эта строка соединения хранится в файле App.config проекта.  

## <a name="see-also"></a>См. также

- [Моделирование и сопоставление](modeling-and-mapping.md)
- [Практическое руководство. Определение строки подключения](how-to-define-the-connection-string.md)
- [Практическое руководство. Создание строки подключения EntityConnection](how-to-build-an-entityconnection-connection-string.md)
- [Средства EDM ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
