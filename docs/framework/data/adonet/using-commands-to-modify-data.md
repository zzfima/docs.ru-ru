---
title: Использование команд для изменения данных
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: 34c73549f18cd4bebb8caf842b252828b7f0a185
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780561"
---
# <a name="using-commands-to-modify-data"></a>Использование команд для изменения данных
Используя поставщик данных .NET Framework, можно выполнять хранимые процедуры или инструкции языка описания данных DDL (например, CREATE TABLE и ALTER COLUMN) для выполнения операций со схемой в базе данных или в каталоге. Эти команды не возвращают строки в виде запроса, поэтому объект **Command** предоставляет **ExecuteNonQuery** для их обработки.  
  
 Кроме использования функции **ExecuteNonQuery** для изменения схемы, этот метод можно также использовать для обработки инструкций SQL, которые изменяют данные, но не возвращают строки, такие как INSERT, Update и DELETE.  
  
 Хотя метод **ExecuteNonQuery** не возвращает строки, входные и выходные параметры и возвращаемые значения могут передаваться и возвращаться через коллекцию **Parameters** объекта **Command** .  
  
## <a name="in-this-section"></a>В этом разделе  
 [Обновление данных в источнике данных](updating-data-in-a-data-source.md)  
 Описывает выполнение команд или хранимых процедур, которые изменяют данные в базе данных.  
  
 [Выполнение операций каталога](performing-catalog-operations.md)  
 Описывает выполнение команд, которые изменяют схему базы данных.  
  
## <a name="see-also"></a>См. также

- [Извлечение и изменение данных в ADO.NET](retrieving-and-modifying-data.md)
- [Команды и параметры](commands-and-parameters.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
