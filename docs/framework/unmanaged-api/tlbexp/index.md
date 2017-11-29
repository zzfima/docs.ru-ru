---
title: "Вспомогательные функции Tlbexp (справочник по неуправляемым API)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d5d0a0b08be725a50442a3db9f9942bceea7cf8a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a><span data-ttu-id="d92dc-102">Вспомогательные функции Tlbexp (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="d92dc-102">Tlbexp Helper Functions (Unmanaged API Reference)</span></span>
<span data-ttu-id="d92dc-103">[Средство экспорта библиотек типов](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) загружает библиотеку динамической компоновки экспорта библиотек.</span><span class="sxs-lookup"><span data-stu-id="d92dc-103">The [Type Library Exporter tool](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) loads a dynamic link library named TlbRef.dll.</span></span> <span data-ttu-id="d92dc-104">Эта библиотека DLL содержит две вспомогательные функции и интерфейс, который использует средство экспорта во время преобразования сборки типа библиотеки.</span><span class="sxs-lookup"><span data-stu-id="d92dc-104">This DLL contains two helper functions and an interface that the exporter tool uses during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d92dc-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="d92dc-105">In This Section</span></span>  
 [<span data-ttu-id="d92dc-106">Функция GetTypeLibInfo</span><span class="sxs-lookup"><span data-stu-id="d92dc-106">GetTypeLibInfo Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 <span data-ttu-id="d92dc-107">Предоставляет сведения о локализации и операционной системы для библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="d92dc-107">Provides localization and operating system information for a type library.</span></span>  
  
 [<span data-ttu-id="d92dc-108">Функция LoadTypeLibWithResolver</span><span class="sxs-lookup"><span data-stu-id="d92dc-108">LoadTypeLibWithResolver Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 <span data-ttu-id="d92dc-109">Загружает библиотеку, используя реализацию [интерфейс ITypeLibResolver](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) разрешает любые ссылки на библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="d92dc-109">Loads a type library by using an implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any referenced type libraries.</span></span>  
  
 [<span data-ttu-id="d92dc-110">Интерфейс ITypeLibResolver</span><span class="sxs-lookup"><span data-stu-id="d92dc-110">ITypeLibResolver Interface</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 <span data-ttu-id="d92dc-111">Предоставляет [метод ResolveTypeLib](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), который возвращает полный путь библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="d92dc-111">Provides the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), which returns the fully qualified path of a type library.</span></span>
