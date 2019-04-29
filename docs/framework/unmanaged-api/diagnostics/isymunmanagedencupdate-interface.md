---
title: Интерфейс ISymUnmanagedENCUpdate
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate
helpviewer_keywords:
- ISymUnmanagedENCUpdate interface [.NET Framework debugging]
ms.assetid: 63a9ef45-01a6-46da-b958-5c6dc2dc232c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 378322c28d59b2a6e7c09f2f2c4bf55bb019d01d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939702"
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="ed0c0-102">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="ed0c0-102">ISymUnmanagedENCUpdate Interface</span></span>
<span data-ttu-id="ed0c0-103">Предоставляет функции для "Изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="ed0c0-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ed0c0-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ed0c0-104">Methods</span></span>  
  
|<span data-ttu-id="ed0c0-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ed0c0-105">Method</span></span>|<span data-ttu-id="ed0c0-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ed0c0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ed0c0-107">Метод GetLocalVariableCount</span><span class="sxs-lookup"><span data-stu-id="ed0c0-107">GetLocalVariableCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="ed0c0-108">Получает количество локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="ed0c0-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="ed0c0-109">Метод GetLocalVariables</span><span class="sxs-lookup"><span data-stu-id="ed0c0-109">GetLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="ed0c0-110">Возвращает локальные переменные.</span><span class="sxs-lookup"><span data-stu-id="ed0c0-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="ed0c0-111">Метод InitializeForEnc</span><span class="sxs-lookup"><span data-stu-id="ed0c0-111">InitializeForEnc Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="ed0c0-112">Позволяет границах методов должны быть вычислены до первого вызова [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="ed0c0-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="ed0c0-113">Метод UpdateMethodLines</span><span class="sxs-lookup"><span data-stu-id="ed0c0-113">UpdateMethodLines Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="ed0c0-114">Позволяет обновлять данные строки для метода, который не был повторно скомпилирован, но его строки были перемещены независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="ed0c0-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="ed0c0-115">Допускается разницы для каждой инструкции.</span><span class="sxs-lookup"><span data-stu-id="ed0c0-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="ed0c0-116">Метод UpdateSymbolStore2</span><span class="sxs-lookup"><span data-stu-id="ed0c0-116">UpdateSymbolStore2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="ed0c0-117">Позволяет компилятору выполнять пропускать функции, которые не были изменены из потока базы данных (PDB) программы, при условии, что сведения о строке соответствует требованиям.</span><span class="sxs-lookup"><span data-stu-id="ed0c0-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="ed0c0-118">Правильные сведения строки можно определить с помощью старых сведений строки PDB и одного разностного для всех строк в функции.</span><span class="sxs-lookup"><span data-stu-id="ed0c0-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ed0c0-119">Требования</span><span class="sxs-lookup"><span data-stu-id="ed0c0-119">Requirements</span></span>  
 <span data-ttu-id="ed0c0-120">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ed0c0-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed0c0-121">См. также</span><span class="sxs-lookup"><span data-stu-id="ed0c0-121">See also</span></span>

- [<span data-ttu-id="ed0c0-122">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="ed0c0-122">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
