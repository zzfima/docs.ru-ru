---
title: Вспомогательные функции Tlbexp (справочник по неуправляемым API)
ms.date: 03/30/2017
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
ms.openlocfilehash: cbde2af9c8a03e6c41f571120027030713f1b8d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73104117"
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a>Вспомогательные функции Tlbexp (справочник по неуправляемым API)
[Средство экспорта библиотек типов](../../tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) загружает библиотеку динамической компоновки TlbRef.dll. Эта библиотека DLL имеет две вспомогательные функции и интерфейс, который использует средство экспорта в ходе преобразования сборки в библиотеку типов.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Функция GetTypeLibInfo](gettypelibinfo-function.md)  
 Предоставляет сведения о локализации и операционной системе для библиотеки типов.  
  
 [Функция LoadTypeLibWithResolver](loadtypelibwithresolver-function.md)  
 Загружает библиотеку типов, используя реализацию [интерфейса ITypeLibResolver](itypelibresolver-interface.md) для разрешения указанных библиотек типов.  
  
 [Интерфейс ITypeLibResolver](itypelibresolver-interface.md)  
 Предоставляет [метод ResolveTypeLib](resolvetypelib-method.md), который возвращает полный путь к библиотеке типов.
