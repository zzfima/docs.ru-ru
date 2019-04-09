---
title: Использование команд для изменения данных
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: f2e3d162bfbdcb79cfecefa4ddc8e6a0dc46ee3c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102457"
---
# <a name="using-commands-to-modify-data"></a>Использование команд для изменения данных
Используя поставщик данных .NET Framework, можно выполнять хранимые процедуры или инструкции языка описания данных DDL (например, CREATE TABLE и ALTER COLUMN) для выполнения операций со схемой в базе данных или в каталоге. Эти команды не возвращают строки, как запрос, поэтому **команда** предоставляет **ExecuteNonQuery** для их обработки.  
  
 Помимо использования **ExecuteNonQuery** для изменения схемы, можно также использовать этот метод для обработки инструкций SQL, которые изменяют данные, но не возвращают строки, например INSERT, UPDATE и удаления.  
  
 Несмотря на то, что строки не возвращаются таблицей **ExecuteNonQuery** метод, входные и выходные параметры и возвращаемые значения могут передаваться и возвращаться через **параметры** коллекцию **команды**  объекта.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Обновление данных в источнике данных](../../../../docs/framework/data/adonet/updating-data-in-a-data-source.md)  
 Описывает выполнение команд или хранимых процедур, которые изменяют данные в базе данных.  
  
 [Выполнение операций каталога](../../../../docs/framework/data/adonet/performing-catalog-operations.md)  
 Описывает выполнение команд, которые изменяют схему базы данных.  
  
## <a name="see-also"></a>См. также

- [Извлечение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Команды и параметры](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [Управляемые поставщики ADO.NET и центр разработчиков DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
