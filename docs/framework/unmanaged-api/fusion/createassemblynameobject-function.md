---
title: Функция CreateAssemblyNameObject
ms.date: 03/30/2017
api_name:
- CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyNameObject
helpviewer_keywords:
- CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb53014a28fb291b8463535addfb61e62d32d7d6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795352"
---
# <a name="createassemblynameobject-function"></a>Функция CreateAssemblyNameObject
Возвращает указатель интерфейса на экземпляр [IAssemblyName](iassemblyname-interface.md) , представляющий уникальный идентификатор сборки с указанным именем.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a>Параметры  
 `ppAssemblyNameObj`  
 заполняет Возвращаемое `IAssemblyName`значение.  
  
 `szAssemblyName`  
 окне Имя сборки, для которой создается новый `IAssemblyName` экземпляр.  
  
 `dwFlags`  
 окне Флаги, передаваемые в конструктор объектов.  
  
 `pvReserved`  
 окне Зарезервировано для будущего расширения. `pvReserved`должен быть пустой ссылкой.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** Fusion. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IAssemblyName](iassemblyname-interface.md)
- [Глобальные статические функции Fusion](fusion-global-static-functions.md)
