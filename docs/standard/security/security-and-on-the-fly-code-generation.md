---
title: Безопасность и создание кода "на лету"
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- code security, on-the-fly code generation
- on-the-fly code generation
- security [.NET Framework], on-the-fly code generation
- secure coding, on-the-fly code generation
ms.assetid: 6d221724-bb21-4d76-90c3-0ee2a2e69be2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ffb1081c80c31353ad38080ae16ef9f8a74b5481
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44046779"
---
# <a name="security-and-on-the-fly-code-generation"></a><span data-ttu-id="1bc04-102">Безопасность и создание кода "на лету"</span><span class="sxs-lookup"><span data-stu-id="1bc04-102">Security and On-the-Fly Code Generation</span></span>
<span data-ttu-id="1bc04-103">Некоторые библиотеки создают и запускают код, выполняя определенную операцию для вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="1bc04-103">Some libraries operate by generating code and running it to perform some operation for the caller.</span></span> <span data-ttu-id="1bc04-104">Основная проблема заключается в создании кода от имени кода с более низким уровнем доверия и его выполнении в среде с более высоким доверием.</span><span class="sxs-lookup"><span data-stu-id="1bc04-104">The basic problem is generating code on behalf of lesser-trust code and running it at a higher trust.</span></span> <span data-ttu-id="1bc04-105">Проблема усугубляется, если вызывающий объект может влиять на создание кода. Поэтому необходимо убедиться в том, что создается только код, который вы считаете безопасным.</span><span class="sxs-lookup"><span data-stu-id="1bc04-105">The problem worsens when the caller can influence code generation, so you must ensure that only code you consider safe is generated.</span></span>  
  
 <span data-ttu-id="1bc04-106">Всегда нужно точно знать, какой код вы создаете.</span><span class="sxs-lookup"><span data-stu-id="1bc04-106">You need to know exactly what code you are generating at all times.</span></span> <span data-ttu-id="1bc04-107">Это означает, что необходимо строго контролировать любые значения, получаемые от пользователя, будь то заключенные в кавычки строки (которые следует преобразовывать в escape-последовательности, чтобы исключить неожиданные элементы кода), идентификаторы (которые необходимо проверять на допустимость) и любые другие элементы.</span><span class="sxs-lookup"><span data-stu-id="1bc04-107">This means that you must have strict controls on any values that you get from a user, be they quote-enclosed strings (which should be escaped so they cannot include unexpected code elements), identifiers (which should be checked to verify that they are valid identifiers), or anything else.</span></span> <span data-ttu-id="1bc04-108">Идентификаторы могут представлять опасность, так как скомпилированную сборку можно изменить так, чтобы ее идентификаторы содержали необычные символы, что, вероятно, нарушит работу сборки (хотя во многих случаях это не создает уязвимости в защите).</span><span class="sxs-lookup"><span data-stu-id="1bc04-108">Identifiers can be dangerous because a compiled assembly can be modified so that its identifiers contain strange characters, which will probably break it (although this is rarely a security vulnerability).</span></span>  
  
 <span data-ttu-id="1bc04-109">Рекомендуется создавать код с помощью порождаемого отражения, что позволяет избежать многих описанных выше проблем.</span><span class="sxs-lookup"><span data-stu-id="1bc04-109">It is recommended that you generate code with reflection emit, which often helps you avoid many of these problems.</span></span>  
  
 <span data-ttu-id="1bc04-110">При компиляции кода необходимо учитывать даже малейшую вероятность его изменения вредоносной программой.</span><span class="sxs-lookup"><span data-stu-id="1bc04-110">When you compile the code, consider whether there is some way a malicious program could modify it.</span></span> <span data-ttu-id="1bc04-111">Существует ли хотя бы небольшой промежуток времени, в течение которого вредоносный код может изменить исходный код на диске до того, как тот будет считан компилятором, или до загрузки DLL-файла этим кодом?</span><span class="sxs-lookup"><span data-stu-id="1bc04-111">Is there a small window of time during which malicious code can change source code on disk before the compiler reads it or before your code loads the .dll file?</span></span> <span data-ttu-id="1bc04-112">Если да, нужно защитить каталог, в котором хранятся эти файлы, с помощью списка управления доступом в файловой системе в зависимости от обстоятельств.</span><span class="sxs-lookup"><span data-stu-id="1bc04-112">If so, you must protect the directory containing these files, using an Access Control List in the file system, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bc04-113">См. также</span><span class="sxs-lookup"><span data-stu-id="1bc04-113">See also</span></span>

- [<span data-ttu-id="1bc04-114">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="1bc04-114">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
