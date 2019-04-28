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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61909393"
---
# <a name="creating-a-cryptographic-scheme"></a><span data-ttu-id="23db4-102">Создание криптографической схемы</span><span class="sxs-lookup"><span data-stu-id="23db4-102">Creating a Cryptographic Scheme</span></span>
<span data-ttu-id="23db4-103">Криптографические компоненты платформы .NET Framework можно объединить для создания различных схем шифрования и расшифровки данных.</span><span class="sxs-lookup"><span data-stu-id="23db4-103">The cryptographic components of the .NET Framework can be combined to create different schemes to encrypt and decrypt data.</span></span>  
  
 <span data-ttu-id="23db4-104">Простая криптографическая схема для шифрования и расшифровки данных может содержать следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="23db4-104">A simple cryptographic scheme for encrypting and decrypting data might specify the following steps:</span></span>  
  
1. <span data-ttu-id="23db4-105">Каждая сторона создает пару из открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="23db4-105">Each party generates a public/private key pair.</span></span>  
  
2. <span data-ttu-id="23db4-106">Стороны обмениваются своими открытыми ключами.</span><span class="sxs-lookup"><span data-stu-id="23db4-106">The parties exchange their public keys.</span></span>  
  
3. <span data-ttu-id="23db4-107">Каждая сторона создает секретный ключ для шифрования методом TripleDES и затем шифрует этот ключ при помощи открытого ключа другой стороны.</span><span class="sxs-lookup"><span data-stu-id="23db4-107">Each party generates a secret key for TripleDES encryption, for example, and encrypts the newly created key using the other's public key.</span></span>  
  
4. <span data-ttu-id="23db4-108">Каждая сторона отправляет данные другой стороне и объединяет ее секретный ключ со своим собственным в определенном порядке, чтобы создать новый секретный ключ.</span><span class="sxs-lookup"><span data-stu-id="23db4-108">Each party sends the data to the other and combines the other's secret key with its own, in a particular order, to create a new secret key.</span></span>  
  
5. <span data-ttu-id="23db4-109">Затем стороны осуществляют взаимодействие с использованием симметричного шифрования.</span><span class="sxs-lookup"><span data-stu-id="23db4-109">The parties then initiate a conversation using symmetric encryption.</span></span>  
  
 <span data-ttu-id="23db4-110">Создание криптографической схемы нельзя назвать тривиальной задачей.</span><span class="sxs-lookup"><span data-stu-id="23db4-110">Creating a cryptographic scheme is not a trivial task.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="23db4-111">См. также</span><span class="sxs-lookup"><span data-stu-id="23db4-111">See also</span></span>

- [<span data-ttu-id="23db4-112">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="23db4-112">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
