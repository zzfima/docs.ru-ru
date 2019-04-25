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
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a><span data-ttu-id="fc9e7-102">Вспомогательные функции Tlbexp (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="fc9e7-102">Tlbexp Helper Functions (Unmanaged API Reference)</span></span>
<span data-ttu-id="fc9e7-103">[Средство экспорта библиотек типов](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) загружает библиотеку динамической компоновки TlbRef.dll.</span><span class="sxs-lookup"><span data-stu-id="fc9e7-103">The [Type Library Exporter tool](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) loads a dynamic link library named TlbRef.dll.</span></span> <span data-ttu-id="fc9e7-104">Эта библиотека DLL имеет две вспомогательные функции и интерфейс, который использует средство экспорта в ходе преобразования сборки в библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="fc9e7-104">This DLL contains two helper functions and an interface that the exporter tool uses during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fc9e7-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="fc9e7-105">In This Section</span></span>  
 [<span data-ttu-id="fc9e7-106">Функция GetTypeLibInfo</span><span class="sxs-lookup"><span data-stu-id="fc9e7-106">GetTypeLibInfo Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 <span data-ttu-id="fc9e7-107">Предоставляет сведения о локализации и операционной системе для библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="fc9e7-107">Provides localization and operating system information for a type library.</span></span>  
  
 [<span data-ttu-id="fc9e7-108">Функция LoadTypeLibWithResolver</span><span class="sxs-lookup"><span data-stu-id="fc9e7-108">LoadTypeLibWithResolver Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 <span data-ttu-id="fc9e7-109">Загружает библиотеку типов, используя реализацию [интерфейса ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) для разрешения указанных библиотек типов.</span><span class="sxs-lookup"><span data-stu-id="fc9e7-109">Loads a type library by using an implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any referenced type libraries.</span></span>  
  
 [<span data-ttu-id="fc9e7-110">Интерфейс ITypeLibResolver</span><span class="sxs-lookup"><span data-stu-id="fc9e7-110">ITypeLibResolver Interface</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 <span data-ttu-id="fc9e7-111">Предоставляет [метод ResolveTypeLib](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), который возвращает полный путь к библиотеке типов.</span><span class="sxs-lookup"><span data-stu-id="fc9e7-111">Provides the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), which returns the fully qualified path of a type library.</span></span>
