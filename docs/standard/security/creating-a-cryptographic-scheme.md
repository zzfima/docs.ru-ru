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
ms.openlocfilehash: 3ef3741ef5cec720c2fb285c9aa60d610acc0be9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321657"
---
# <a name="creating-a-cryptographic-scheme"></a>Создание криптографической схемы
Криптографические компоненты платформы .NET Framework можно объединить для создания различных схем шифрования и расшифровки данных.  
  
 Простая криптографическая схема для шифрования и расшифровки данных может содержать следующие шаги.  
  
1. Каждая сторона создает пару из открытого и закрытого ключей.  
  
2. Стороны обмениваются своими открытыми ключами.  
  
3. Каждая сторона создает секретный ключ для шифрования методом TripleDES и затем шифрует этот ключ при помощи открытого ключа другой стороны.  
  
4. Каждая сторона отправляет данные другой стороне и объединяет ее секретный ключ со своим собственным в определенном порядке, чтобы создать новый секретный ключ.  
  
5. Затем стороны осуществляют взаимодействие с использованием симметричного шифрования.  
  
 Создание криптографической схемы нельзя назвать тривиальной задачей.
  
## <a name="see-also"></a>См. также

- [службы шифрования](../../../docs/standard/security/cryptographic-services.md)
