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
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a><span data-ttu-id="44fde-102">Вспомогательные функции Tlbexp (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="44fde-102">Tlbexp Helper Functions (Unmanaged API Reference)</span></span>
<span data-ttu-id="44fde-103">[Средство экспорта библиотек типов](../../tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) загружает библиотеку динамической компоновки TlbRef.dll.</span><span class="sxs-lookup"><span data-stu-id="44fde-103">The [Type Library Exporter tool](../../tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) loads a dynamic link library named TlbRef.dll.</span></span> <span data-ttu-id="44fde-104">Эта библиотека DLL имеет две вспомогательные функции и интерфейс, который использует средство экспорта в ходе преобразования сборки в библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="44fde-104">This DLL contains two helper functions and an interface that the exporter tool uses during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="44fde-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="44fde-105">In This Section</span></span>  
 [<span data-ttu-id="44fde-106">Функция GetTypeLibInfo</span><span class="sxs-lookup"><span data-stu-id="44fde-106">GetTypeLibInfo Function</span></span>](gettypelibinfo-function.md)  
 <span data-ttu-id="44fde-107">Предоставляет сведения о локализации и операционной системе для библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="44fde-107">Provides localization and operating system information for a type library.</span></span>  
  
 [<span data-ttu-id="44fde-108">Функция LoadTypeLibWithResolver</span><span class="sxs-lookup"><span data-stu-id="44fde-108">LoadTypeLibWithResolver Function</span></span>](loadtypelibwithresolver-function.md)  
 <span data-ttu-id="44fde-109">Загружает библиотеку типов, используя реализацию [интерфейса ITypeLibResolver](itypelibresolver-interface.md) для разрешения указанных библиотек типов.</span><span class="sxs-lookup"><span data-stu-id="44fde-109">Loads a type library by using an implementation of the [ITypeLibResolver interface](itypelibresolver-interface.md) to resolve any referenced type libraries.</span></span>  
  
 [<span data-ttu-id="44fde-110">Интерфейс ITypeLibResolver</span><span class="sxs-lookup"><span data-stu-id="44fde-110">ITypeLibResolver Interface</span></span>](itypelibresolver-interface.md)  
 <span data-ttu-id="44fde-111">Предоставляет [метод ResolveTypeLib](resolvetypelib-method.md), который возвращает полный путь к библиотеке типов.</span><span class="sxs-lookup"><span data-stu-id="44fde-111">Provides the [ResolveTypeLib method](resolvetypelib-method.md), which returns the fully qualified path of a type library.</span></span>
