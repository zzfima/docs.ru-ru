---
title: Функция CreateInstallReferenceEnum
ms.date: 03/30/2017
api_name:
- CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstallReference
helpviewer_keywords:
- CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type:
- apiref
ms.openlocfilehash: f089769f854bad5d3e572e0307734e06e72ca89c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108571"
---
# <a name="createinstallreferenceenum-function"></a>Функция CreateInstallReferenceEnum
Возвращает указатель на экземпляр [IInstallReferenceEnum](iinstallreferenceenum-interface.md) , представляющий список ссылок приложения на указанную сборку.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a>Параметры  
 `ppRefEnum`  
 заполняет Возвращаемый указатель `IInstallReferenceEnum`.  
  
 `pName`  
 окне Объект [IAssemblyName](iassemblyname-interface.md) , определяющий сборку, для которой перечисляются ссылки.  
  
 `dwFlags`  
 окне Флаги, влияющие на поведение перечислителя.  
  
 `pvReserved`  
 окне Зарезервировано для будущего расширения. `pvReserved` должен быть пустой ссылкой.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Библиотека:** Fusion. dll и mscorwks. dll. Используйте Fusion. dll вместо Mscorwks. dll, чтобы обеспечить правильную версию .NET Framework.  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IInstallReferenceEnum](iinstallreferenceenum-interface.md)
- [Интерфейс IAssemblyName](iassemblyname-interface.md)
- [Глобальные статические функции Fusion](fusion-global-static-functions.md)
