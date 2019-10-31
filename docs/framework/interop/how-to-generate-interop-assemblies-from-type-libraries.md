---
title: Практическое руководство. Создание сборок взаимодействия их библиотек типов
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- Type Library Importer
- type libraries
- COM interop, importing type library
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
ms.openlocfilehash: 7cca21630bd1dbd6896f882d058f288f603e95df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123895"
---
# <a name="how-to-generate-interop-assemblies-from-type-libraries"></a>Практическое руководство. Создание сборок взаимодействия их библиотек типов
[Программа импорта библиотек типов (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) — это средство командной строки, которое преобразует коклассы и интерфейсы, содержащиеся в библиотеке типов COM, в метаданные. Это средство автоматически создает сборку взаимодействия и пространство имен для сведений о типе. После того как метаданные класса стали доступными, управляемые клиенты могут создавать экземпляры типа COM и вызывать его методы, как если бы это был экземпляр .NET. Средство Tlbimp.exe преобразует всю библиотеку типов в метаданные за один раз и не может создать сведения о типах для подмножества типов, определенных в библиотеке типов.  
  
### <a name="to-generate-an-interop-assembly-from-a-type-library"></a>Создание сборки взаимодействия из библиотеки типов  
  
1. Используйте следующую команду:  
  
     **tlbimp** \<*файл_библиотеки_типов*>  
  
     При указании параметра **/out:** создается сборка взаимодействия с измененным именем, например LOANLib.dll. Изменение имени сборки взаимодействия помогает отличить эту сборку от исходного файла DLL COM и избежать возможных проблем с повторяющимися именами.  
  
## <a name="example"></a>Пример  
 Следующая команда создает сборку Loanlib.dll в пространстве имен `Loanlib`.  
  
```  
tlbimp Loanlib.tlb  
```  
  
 Следующая команда создает сборку взаимодействия с измененным именем (LOANLib.dll).  
  
```  
tlbimp LoanLib.tlb /out: LOANLib.dll  
```  
  
## <a name="see-also"></a>См. также

- [Импорт библиотеки типов в виде сборки](importing-a-type-library-as-an-assembly.md)
- [Предоставление COM-компонентов платформе .NET Framework](exposing-com-components.md)
