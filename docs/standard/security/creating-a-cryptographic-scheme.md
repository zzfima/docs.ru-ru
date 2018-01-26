---
title: "Создание криптографической схемы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- encryption [.NET Framework], creating cryptographic schemes
- cryptography [.NET Framework], creating cryptographic schemes
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b0aabdc9150aea73ad9078b0e9ee92b2abd03e17
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="creating-a-cryptographic-scheme"></a>Создание криптографической схемы
Криптографические компоненты платформы .NET Framework можно объединить для создания различных схем шифрования и расшифровки данных.  
  
 Простая криптографическая схема для шифрования и расшифровки данных может содержать следующие шаги.  
  
1.  Каждая сторона создает пару из открытого и закрытого ключей.  
  
2.  Стороны обмениваются своими открытыми ключами.  
  
3.  Каждая сторона создает секретный ключ для шифрования методом TripleDES и затем шифрует этот ключ при помощи открытого ключа другой стороны.  
  
4.  Каждая сторона отправляет данные другой стороне и объединяет ее секретный ключ со своим собственным в определенном порядке, чтобы создать новый секретный ключ.  
  
5.  Затем стороны осуществляют взаимодействие с использованием симметричного шифрования.  
  
 Создание криптографической схемы нельзя назвать тривиальной задачей. Дополнительные сведения об использовании криптографии см. в разделе «Шифрование» в документации к пакету SDK для платформы на сайте http://MSDN.Microsoft.com/library.  
  
## <a name="see-also"></a>См. также  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
