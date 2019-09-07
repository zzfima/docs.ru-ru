---
title: Вспомогательные функции Tlbexp (справочник по неуправляемым API)
ms.date: 03/30/2017
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a95ff535a4d0847fbd4b8af28f873b67a1829a4f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798833"
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
