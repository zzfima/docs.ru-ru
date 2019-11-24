---
title: Интерфейс ISymUnmanagedVariable
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
ms.openlocfilehash: ee57ba14f048032e2cd9d0129089743c0f0304bc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445973"
---
# <a name="isymunmanagedvariable-interface"></a>Интерфейс ISymUnmanagedVariable
Represents a variable, such as a parameter, a local variable, or a field.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetAddressField1](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|Gets the first address field for this variable. Its meaning depends on the kind of address.|  
|[Метод GetAddressField2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|Gets the second address field for this variable. Its meaning depends on the kind of address.|  
|[Метод GetAddressField3](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|Gets the third address field for this variable. Its meaning depends on the kind of address.|  
|[Метод GetAddressKind](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|Gets the kind of address of this variable.|  
|[Метод GetAttributes](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|Gets the attribute flags for this variable.|  
|[Метод GetEndOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|Gets the end offset of this variable within its parent.|  
|[Метод GetName](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|Gets the name of this variable.|  
|[Метод GetSignature](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|Gets the signature of this variable.|  
|[Метод GetStartOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|Gets the start offset of this variable within its parent.|  
  
## <a name="requirements"></a>Требования  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также

- [Интерфейсы хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
