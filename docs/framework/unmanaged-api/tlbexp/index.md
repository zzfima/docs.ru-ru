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
ms.openlocfilehash: 9f41a233e9b5338bdb0a324ff9af267a97821d4e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967704"
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a>Вспомогательные функции Tlbexp (справочник по неуправляемым API)
[Средство экспорта библиотек типов](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) загружает библиотеку динамической компоновки TlbRef.dll. Эта библиотека DLL имеет две вспомогательные функции и интерфейс, который использует средство экспорта в ходе преобразования сборки в библиотеку типов.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Функция GetTypeLibInfo](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 Предоставляет сведения о локализации и операционной системе для библиотеки типов.  
  
 [Функция LoadTypeLibWithResolver](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 Загружает библиотеку типов, используя реализацию [интерфейса ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) для разрешения указанных библиотек типов.  
  
 [Интерфейс ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 Предоставляет [метод ResolveTypeLib](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), который возвращает полный путь к библиотеке типов.
