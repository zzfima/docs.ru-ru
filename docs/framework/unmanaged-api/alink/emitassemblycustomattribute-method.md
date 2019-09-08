---
title: Метод EmitAssemblyCustomAttribute
ms.date: 03/30/2017
api_name:
- IALink.EmitAssemblyCustomAttribute
- EmitAssemblyCustomAttribute
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssemblyCustomAttribute
helpviewer_keywords:
- EmitAssemblyCustomAttribute method
ms.assetid: b72f5409-79af-4fa7-90a7-7630eec170f1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 77d54f6c8f67dda5132518d1fbd579a91ce82071
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777439"
---
# <a name="emitassemblycustomattribute-method"></a>Метод EmitAssemblyCustomAttribute
Вызовите метод, чтобы установить настраиваемые атрибуты уровня сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EmitAssemblyCustomAttribute(  
    mdAssembly   AssemblyID,  
    mdToken      FileToken,  
    mdToken      tkType,  
    void const*  pCustomValue,  
    DWORD        cbCustomValue,  
    BOOL         bSecurity,  
    BOOL         bAllowMulti  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  
 `AssemblyID`  
 Идентификатор сборки.  
  
 `FileToken`  
 Файл, который разфайлет атрибут. Может иметь значение NULL `AssemblyID` , если не указывает на непривязанный netmodule.  
  
 `tkType`  
 Тип настраиваемого атрибута.  
  
 `pCustomValue`  
 Пользовательские данные значения.  
  
 `cbCustomValue`  
 Длина данных пользовательского значения.  
  
 `bSecurity`  
 Значение TRUE, если настраиваемый атрибут связан с подписыванием сборки.  
  
 `bAllowMulti`  
 Значение TRUE, если требуется выдавать несколько атрибутов.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается с ошибкой, возвращает значение S_OK.  
  
## <a name="requirements"></a>Требования  
 Требуется ALink. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)
