---
title: Указатель функции LPOVERLAPPED_COMPLETION_ROUTINE
ms.date: 03/30/2017
api_name:
- LPOVERLAPPED_COMPLETION_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE
helpviewer_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 5fb645d9-b818-401c-8c2c-c30d86de58ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd4b7ffef9c0ba3aba54387245b2d5c9ec1ae906
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441760"
---
# <a name="lpoverlappedcompletionroutine-function-pointer"></a>Указатель функции LPOVERLAPPED_COMPLETION_ROUTINE
Указывает на функцию, которая уведомляет основное приложение перекрывающегося (то есть асинхронные) завершения ввода-вывода на устройстве.  
  
 Указатель на функцию рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `dwErrorCode`  
 [in] Значение, которое представляет собой код ошибки, если устройство было закрыто; в противном случае это значение равно нулю.  
  
 Закрытие устройства приводит к немедленному завершению всех ожидающих операций ввода-вывода на устройстве.  
  
 `dwNumberOfBytesTransfered`  
 [in] Число байтов, переданных в операции ввода-вывода.  
  
 `lpOverlapped`  
 [in] Указатель на структуру, содержащую информацию, используемую для выполнения запроса ввода-вывода.  
  
## <a name="remarks"></a>Примечания  
 Функция, к которому `LPOVERLAPPED_COMPLETION_ROUTINE` точек — функция обратного вызова и должны быть реализованы разработчиком ведущего приложения. Функция обратного вызова позволяет основному приложению обработать выполненный запрос ввода-вывода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorWks.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
