---
title: Создание криптографической схемы
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- encryption [.NET Framework], creating cryptographic schemes
- cryptography [.NET Framework], creating cryptographic schemes
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b1635276465dd58028c8a5e4b7e69a307664a4c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="creating-a-cryptographic-scheme"></a>Создание криптографической схемы
Криптографические компоненты платформы .NET Framework можно объединить для создания различных схем шифрования и расшифровки данных.  
  
 Простая криптографическая схема для шифрования и расшифровки данных может содержать следующие шаги.  
  
1.  Каждая сторона создает пару из открытого и закрытого ключей.  
  
2.  Стороны обмениваются своими открытыми ключами.  
  
3.  Каждая сторона создает секретный ключ для шифрования методом TripleDES и затем шифрует этот ключ при помощи открытого ключа другой стороны.  
  
4.  Каждая сторона отправляет данные другой стороне и объединяет ее секретный ключ со своим собственным в определенном порядке, чтобы создать новый секретный ключ.  
  
5.  Затем стороны осуществляют взаимодействие с использованием симметричного шифрования.  
  
 Создание криптографической схемы нельзя назвать тривиальной задачей. Дополнительные сведения об использовании криптографии см. в разделе шифрования в документации Platform SDK в http://msdn.microsoft.com/library.  
  
## <a name="see-also"></a>См. также  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
