---
title: "Метод ISymUnmanagedReader2::GetSymAttributePreRemap"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader2.GetSymAttributePreRemap
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader2::GetSymAttributePreRemap
helpviewer_keywords:
- GetSymAttributePreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetSymAttributePreRemap method [.NET Framework debugging]
ms.assetid: 7580d546-a709-40c5-ad02-aa70d774fd0b
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 75608d89b6fd34570166718de824150b0621c84e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a>Метод ISymUnmanagedReader2::GetSymAttributePreRemap
Получает пользовательский атрибут на основе его имени. В отличие от настраиваемых атрибутов метаданных эти атрибуты хранятся в хранилище символов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 `parent`  
 [in] Токен метаданных родительского элемента.  
  
 `name`  
 [in] Указатель на `WCHAR` , содержащее имя.  
  
 `cBuffer`  
 [in] Объект `ULONG32` указывает размер `buffer` массива.  
  
 `pcBuffer`  
 [out] Указатель на `ULONG32` , получающий размер буфера, который должен содержать атрибут байт.  
  
 `buffer`  
 [out] Указатель на буфер, в который помещаются байты атрибута.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ISymUnmanagedReader2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
