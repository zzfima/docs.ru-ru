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
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a><span data-ttu-id="4c984-102">Вспомогательные функции Tlbexp (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="4c984-102">Tlbexp Helper Functions (Unmanaged API Reference)</span></span>
<span data-ttu-id="4c984-103">[Средство экспорта библиотек типов](../../tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) загружает библиотеку динамической компоновки TlbRef.dll.</span><span class="sxs-lookup"><span data-stu-id="4c984-103">The [Type Library Exporter tool](../../tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) loads a dynamic link library named TlbRef.dll.</span></span> <span data-ttu-id="4c984-104">Эта библиотека DLL имеет две вспомогательные функции и интерфейс, который использует средство экспорта в ходе преобразования сборки в библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="4c984-104">This DLL contains two helper functions and an interface that the exporter tool uses during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4c984-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="4c984-105">In This Section</span></span>  
 [<span data-ttu-id="4c984-106">Функция GetTypeLibInfo</span><span class="sxs-lookup"><span data-stu-id="4c984-106">GetTypeLibInfo Function</span></span>](gettypelibinfo-function.md)  
 <span data-ttu-id="4c984-107">Предоставляет сведения о локализации и операционной системе для библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="4c984-107">Provides localization and operating system information for a type library.</span></span>  
  
 [<span data-ttu-id="4c984-108">Функция LoadTypeLibWithResolver</span><span class="sxs-lookup"><span data-stu-id="4c984-108">LoadTypeLibWithResolver Function</span></span>](loadtypelibwithresolver-function.md)  
 <span data-ttu-id="4c984-109">Загружает библиотеку типов, используя реализацию [интерфейса ITypeLibResolver](itypelibresolver-interface.md) для разрешения указанных библиотек типов.</span><span class="sxs-lookup"><span data-stu-id="4c984-109">Loads a type library by using an implementation of the [ITypeLibResolver interface](itypelibresolver-interface.md) to resolve any referenced type libraries.</span></span>  
  
 [<span data-ttu-id="4c984-110">Интерфейс ITypeLibResolver</span><span class="sxs-lookup"><span data-stu-id="4c984-110">ITypeLibResolver Interface</span></span>](itypelibresolver-interface.md)  
 <span data-ttu-id="4c984-111">Предоставляет [метод ResolveTypeLib](resolvetypelib-method.md), который возвращает полный путь к библиотеке типов.</span><span class="sxs-lookup"><span data-stu-id="4c984-111">Provides the [ResolveTypeLib method](resolvetypelib-method.md), which returns the fully qualified path of a type library.</span></span>
