---
title: "Использование неуправляемых функций DLL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unmanaged functions, calling
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- platform invoke, about platform invoke
- DLL functions, consuming unmanaged
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke
- DLL functions
ms.assetid: eca7606e-ebfb-4f47-b8d9-289903fdc045
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6276f2dc2bd57dc3eaf81eb2949e3c1ea3727e69
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="consuming-unmanaged-dll-functions"></a>Использование неуправляемых функций DLL
Вызов неуправляемого кода — это служба, позволяющая управляемому коду вызывать неуправляемые функции, реализованные в библиотеках динамической компоновки (DLL), например функции библиотек Win32 API. Он обнаруживает и вызывает экспортированную функцию и при необходимости маршалирует ее аргументы (целые числа, строки, массивы, структуры и так далее) через границы взаимодействия. Дополнительные сведения об этой службе см. в разделе [Подробный обзор вызова неуправляемого кода](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243).  
  
 В этом разделе представлено несколько задач, связанных с использованием неуправляемых функций DLL. Кроме того, раздел содержит общие сведения и ссылки на дополнительную информацию и примеры.  
  
#### <a name="to-consume-exported-dll-functions"></a>Использование экспортированных функций DLL  
  
1.  [Идентификация функций в библиотеках DLL](../../../docs/framework/interop/identifying-functions-in-dlls.md).  
  
     Как минимум, необходимо указать имя функции и имя библиотеки DLL, содержащей ее.  
  
2.  [Создание класса, содержащего функции DLL](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md).  
  
     Можно использовать существующий класс, создать отдельный класс для каждой неуправляемой функции или создать один класс, содержащий набор связанных неуправляемых функций.  
  
3.  [Создание прототипов в управляемом коде](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).  
  
     [Visual Basic] Используйте оператор **Declare** с ключевыми словами **Function** и **Lib**. В редких случаях можно использовать атрибут **DllImportAttribute** с ключевыми словами **Shared Function**. Такие случаи рассматриваются далее в этом разделе.  
  
     [C#] Используйте атрибут **DllImportAttribute** для идентификации библиотеки DLL и функции. Пометьте метод модификаторами **static** и **extern**.  
  
     [C++] Используйте атрибут **DllImportAttribute** для идентификации библиотеки DLL и функции. Пометьте метод или функцию оболочки модификатором **extern "C"**.  
  
4.  [Вызов функции DLL](../../../docs/framework/interop/calling-a-dll-function.md).  
  
     Вызовите метод управляемого класса так же, как и любой другой управляемый метод. [Передача структур](../../../docs/framework/interop/passing-structures.md) и [реализация функций обратного вызова](../../../docs/framework/interop/callback-functions.md) представляют собой особые случаи.  
  
 Примеры, демонстрирующие создание объявлений на основе .NET, которые используются с вызовом неуправляемого кода, см. в разделе [Маршалинг данных при вызове неуправляемого кода](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).  
  
## <a name="a-closer-look-at-platform-invoke"></a>Подробный обзор вызова неуправляемого кода  
 Вызов неуправляемого кода использует метаданные для нахождения экспортированных функций и маршалинга их аргументов во время выполнения. Данный процесс показан на следующем рисунке.  
  
 ![Платформозависимый вызов](../../../docs/framework/interop/media/pinvoke.gif "pinvoke")  
Вызов неуправляемой функции DLL с помощью вызова неуправляемого кода  
  
 Когда неуправляемый код вызывает неуправляемую функцию, то он выполняет следующую последовательность действий:  
  
1.  Определяет библиотеку DLL, содержащую функцию.  
  
2.  Загружает библиотеку DLL в память.  
  
3.  Находит адрес функции в памяти и помещает ее аргументы в стек, выполнив по необходимости маршалинг данных.  
  
    > [!NOTE]
    >  Поиск и загрузка библиотеки DLL, а также определение адреса функции в памяти выполняются только при первом вызове функции.  
  
4.  Передает управление неуправляемой функции.  
  
 Вызов неуправляемого кода вызывает исключения, создаваемые неуправляемой функцией для управляемого вызывающего объекта.  
  
## <a name="see-also"></a>См. также  
 [Взаимодействие с неуправляемым кодом](../../../docs/framework/interop/index.md)  
 [Примеры вызовов неуправляемого кода](../../../docs/framework/interop/platform-invoke-examples.md)  
 [Маршалинг взаимодействия](../../../docs/framework/interop/interop-marshaling.md)  
 [Использование неуправляемых функций DLL](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)
