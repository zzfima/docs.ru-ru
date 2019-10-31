---
title: Регистрация сборок в COM
ms.date: 03/30/2017
helpviewer_keywords:
- COM interop, registering assemblies
- unregistering assemblies
- interoperation with unmanaged code, registering assemblies
- registering assemblies
ms.assetid: 87925795-a3ae-4833-b138-125413478551
ms.openlocfilehash: 9ff24a5705058d4e303b3b64b454ced8548053a4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73113809"
---
# <a name="registering-assemblies-with-com"></a>Регистрация сборок в COM
С помощью программы командной строки, которая называется [средством регистрации сборок (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md), можно регистрировать сборки для использования с моделью COM и отменять их регистрацию. Программа Regasm.exe добавляет сведения о классе в системный реестр, что обеспечивает прозрачное использование класса .NET Framework COM-клиентами. Класс <xref:System.Runtime.InteropServices.RegistrationServices> реализует эквивалентные функциональные возможности.  
  
 Управляемый компонент необходимо регистрировать в реестре Windows до того, как он будет активироваться из COM-клиента. В следующей таблице показаны разделы, которые программа Regasm.exe обычно добавляет в реестр Windows. (000000 указывает фактическое значение GUID.)  
  
|Идентификатор GUID|Описание|Раздел реестра|  
|----------|-----------------|------------------|  
|CLSID|Идентификатор класса|HKEY_CLASSES_ROOT\CLSID\\{000…000}|  
|IID|Идентификатор интерфейса|HKEY_CLASSES_ROOT\Interface\\{000…000}|  
|LIBID|Идентификатор библиотеки|HKEY_CLASSES_ROOT\TypeLib\\{000…000}|  
|ProgID|Программный идентификатор|HKEY_CLASSES_ROOT\000…000|  
  
 В разделе HKCR\CLSID\\{0000…0000} в качестве значения по умолчанию устанавливается идентификатор ProgID класса, а также добавляются два именованных значения (Class и Assembly). Среда выполнения считывает Assembly из реестра и передает его в средство определения сборок среды выполнения. Средство определения сборок пытается найти сборку по таким сведениям о ней, как имя и номер версии. Средство определения сборок может находить сборки в следующих расположениях:  
  
- Глобальный кэш сборок (для сборок со строгим именем).  
  
- В каталоге приложения. Сборки, загруженные по пути приложения, доступны только из этого приложения.  
  
- По пути к файлу, указанному в параметре **/codebase** программы Regasm.exe.  
  
 Программа Regasm.exe также создает подраздел InProcServer32 в разделе HKCR\CLSID\\{0000…0000}. В качестве значения по умолчанию этому разделу присваивается имя библиотеки DLL, которая инициализирует общеязыковую среду выполнения (Mscoree.dll).  
  
## <a name="examining-registry-entries"></a>Проверка записей реестра  
 COM-взаимодействие предоставляет стандартную реализацию фабрики класса для создания экземпляра любого класса .NET Framework. Клиенты могут вызывать **DllGetClassObject** для управляемой библиотеки DLL, чтобы получить фабрику класса и создать объекты так же, как и для любого другого COM-компонента.  
  
 В подразделе `InprocServer32` вместо традиционной библиотеки типов COM указывается ссылка на библиотеку Mscoree.dll. Это указывает на то, что общеязыковая среда выполнения создает объект.  
  
## <a name="see-also"></a>См. также

- [Предоставление компонентов .NET Framework клиентам COM](exposing-dotnet-components-to-com.md)
- [Практическое руководство. Создание ссылки на типы .NET из COM](how-to-reference-net-types-from-com.md)
- [Вызов объекта .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))
- [Развертывание приложения для доступа к COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))
