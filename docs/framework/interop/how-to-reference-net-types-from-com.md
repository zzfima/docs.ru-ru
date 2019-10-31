---
title: Практическое руководство. Создание ссылки на типы .NET из COM
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- importing type library
- COM interop, referencing .NET types
- interoperation with unmanaged code, referencing .NET types
- referencing .NET types
- interoperation with unmanaged code, importing type library
- type libraries
- COM interop, importing type library
ms.assetid: 54917f6f-cb18-4103-b622-856b55da93f3
ms.openlocfilehash: 0223cb25b933cc84af49aa86d90259fdf1fd3efc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124177"
---
# <a name="how-to-reference-net-types-from-com"></a>Практическое руководство. Создание ссылки на типы .NET из COM
С точки зрения кода клиента и сервера различия между COM и .NET Framework практически незаметны. Клиенты Microsoft Visual Basic могут просматривать объект .NET в обозревателе объектов, который позволяет просмотреть методы, синтаксис, свойства и поля объекта точно так же, как если бы это был объект COM.  
  
 Процесс импорта библиотеки типов для клиентов C++ несколько сложнее, хотя для экспорта метаданных в библиотеку типов COM можно использовать те же средства. Чтобы получить доступ к элементам объекта .NET из неуправляемого клиента C++, укажите ссылку на TLB-файл (файл, созданный с помощью программы Tlbexp.exe) в директиве **#import**. При указании ссылки на библиотеку типов из C++ необходимо указать параметр **raw_interfaces_only** или импортировать определения из библиотеки базовых классов Mscorlib.tlb.  
  
### <a name="to-import-a-library"></a>Импорт библиотеки  
  
- Укажите параметр **raw_interfaces_only** в диалоговом окне директивы **#import**. Пример:  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     \- или -  
  
- Включите директиву #import для Mscorlib.tlb. Пример:  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## <a name="see-also"></a>См. также

- [Предоставление компонентов .NET Framework клиентам COM](exposing-dotnet-components-to-com.md)
- [Регистрация сборок в COM](registering-assemblies-with-com.md)
- [Вызов объекта .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))
- [Развертывание приложения для доступа к COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))
