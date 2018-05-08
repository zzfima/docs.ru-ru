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
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a>Вспомогательные функции Tlbexp (справочник по неуправляемым API)
[Средство экспорта библиотек типов](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) загружает библиотеку динамической компоновки экспорта библиотек. Эта библиотека DLL содержит две вспомогательные функции и интерфейс, который использует средство экспорта во время преобразования сборки типа библиотеки.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Функция GetTypeLibInfo](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 Предоставляет сведения о локализации и операционной системы для библиотеки типов.  
  
 [Функция LoadTypeLibWithResolver](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 Загружает библиотеку, используя реализацию [интерфейс ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) разрешает любые ссылки на библиотеки типов.  
  
 [Интерфейс ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 Предоставляет [метод ResolveTypeLib](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), который возвращает полный путь библиотеки типов.
