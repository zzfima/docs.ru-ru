---
title: Функция StrongNameSignatureVerificationEx
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08247c1ec5b868055e4836b3c0fb520a536374e8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798916"
---
# <a name="strongnamesignatureverificationex-function"></a>Функция StrongNameSignatureVerificationEx
Получает значение, указывающее, содержит ли находящийся по указанному пути манифест сборки подпись строгого имени.  
  
 Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `wszFilePath`  
 окне Путь к переносимому исполняемому файлу (exe или DLL) для проверяемой сборки.  
  
 `fForceVerification`  
 окне значение для выполнения проверки, даже если необходимо переопределить параметры реестра; в противном случае —. `false` `true`  
  
 `pfWasVerified`  
 заполняет `true` значение ,`false`если подпись строгого имени проверена; в противном случае —. `pfWasVerified`также имеет значение `false` , если проверка прошла успешно из-за параметров реестра.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`значение, если проверка прошла успешно; в противном случае —. `false`  
  
## <a name="remarks"></a>Примечания  
 `StrongNameSignatureVerificationEx`предоставляет такую возможность, как функция [StrongNameSignatureVerification](strongnamesignatureverification-function.md) . Однако второй входной параметр и выходной параметр для `StrongNameSignatureVerificationEx` имеют тип `BOOLEAN` , а не `DWORD`.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** StrongName. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку Mscoree. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [Метод StrongNameSignatureVerification](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
