---
title: "Creating a Cryptographic Scheme | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "encryption [.NET Framework], creating cryptographic schemes"
  - "cryptography [.NET Framework], creating cryptographic schemes"
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Creating a Cryptographic Scheme
Криптографические компоненты платформы .NET Framework можно объединить для создания различных схем шифрования и расшифровки данных.  
  
 Простая криптографическая схема для шифрования и расшифровки данных может содержать следующие шаги.  
  
1.  Каждая сторона создает пару из открытого и закрытого ключей.  
  
2.  Стороны обмениваются своими открытыми ключами.  
  
3.  Каждая сторона создает секретный ключ для шифрования методом TripleDES и затем шифрует этот ключ при помощи открытого ключа другой стороны.  
  
4.  Каждая сторона отправляет данные другой стороне и объединяет ее секретный ключ со своим собственным в определенном порядке, чтобы создать новый секретный ключ.  
  
5.  Затем стороны осуществляют взаимодействие с использованием симметричного шифрования.  
  
 Создание криптографической схемы нельзя назвать тривиальной задачей.  Дополнительные сведения об использовании криптографии см. в разделе «Шифрование» в документации к пакету SDK для платформы на сайте http:\/\/MSDN.Microsoft.com\/library.  
  
## См. также  
 [Службы криптографии](../../../docs/standard/security/cryptographic-services.md)