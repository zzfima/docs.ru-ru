---
title: Идентификация функций в библиотеках DLL
ms.date: 03/30/2017
helpviewer_keywords:
- platform invoke, identifying functions
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- identifying DLL functions
- DLL functions
ms.assetid: 3e3f6780-6d90-4413-bad7-ba641220364d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ca01234bf7adaca1337053bbc2bbba0731be3cd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132045"
---
# <a name="identifying-functions-in-dlls"></a>Идентификация функций в библиотеках DLL
Идентификатор функции DLL состоит из следующих элементов:  
  
-   Имя функции или порядковый номер  
  
-   Имя файла DLL, в котором находится реализация  
  
 Например, при указании функции **MessageBox** в библиотеке User32.dll определяется функция (**MessageBox**) и ее расположение (User32.dll, User32 или user32). Программный интерфейс Microsoft Windows (API Windows) может содержать две версии для каждой функции, обрабатывающей символы и строки: версию ANSI для однобайтовых символов и версию Юникода для двухбайтовых символов. Если кодировка не указана, она определяется полем <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> (по умолчанию ANSI). Некоторые функции могут иметь более двух версий.  
  
 **MessageBoxA** — это точка входа ANSI для функции **MessageBox**; **MessageBoxW** — версия для Юникода. Чтобы получить список имен функций в конкретной библиотеке DLL, например user32.dll, можно воспользоваться различными средствами командной строки. Например, для получения имен функций можно воспользоваться `dumpbin /exports user32.dll` или `link /dump /exports user32.dll`.  
  
 Неуправляемую функцию в коде можно переименовать, при условии что новое имя функции соответствует исходной точке входа в библиотеке DLL. Инструкции по переименованию неуправляемой функции DLL в управляемом исходном коде см. в разделе [Указание точки входа](../../../docs/framework/interop/specifying-an-entry-point.md).  
  
 Вызов неуправляемого кода позволяет управлять значительной частью операционной системы с помощью вызова функций в API Windows и других библиотеках DLL. Наряду с API Windows существует несколько других API и библиотек DLL, для которых доступен вызов неуправляемого кода.  
  
 В следующей таблице описаны несколько распространенных библиотек DLL в API Windows.  
  
|DLL|Описание содержимого|  
|---------|-----------------------------|  
|GDI32.dll|Функции интерфейса графических устройств (GDI) для вывода информации на устройство, например функции для рисования и управления шрифтами.|  
|Kernel32.dll|Низкоуровневые функции операционной системы для управления памятью и обработки ресурсов.|  
|User32.dll|Функции управления Windows для обработки сообщений, таймеров, меню и обмена данными.|  
  
 Полную документацию по API Windows см. в разделе "Пакет SDK платформы". Примеры, демонстрирующие создание объявлений на основе .NET, которые используются с вызовом неуправляемого кода, см. в разделе [Маршалинг данных при вызове неуправляемого кода](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).  
  
## <a name="see-also"></a>См. также

- [Использование неуправляемых функций DLL](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)
- [Задание точки входа](../../../docs/framework/interop/specifying-an-entry-point.md)
- [Создание класса, содержащего функции DLL](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md)
- [Создание прототипов в управляемом коде](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)
- [Вызов функции DLL](../../../docs/framework/interop/calling-a-dll-function.md)
