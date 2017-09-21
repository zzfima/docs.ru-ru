---
title: "-highentropyva (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /highentropyva
dev_langs:
- CSharp
helpviewer_keywords:
- /highentropyva compiler option [C#]
- -highentropyva compiler option [C#]
- highentropyva compiler option [C#]
ms.assetid: eaf409b3-384e-49dd-9417-62453658f421
caps.latest.revision: 8
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4cb21c109fc33a30da016fd6a42285a3a3da02e2
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="highentropyva-c-compiler-options"></a>/highentropyva (параметры компилятора C#)
Параметр компилятора **/highentropyva** сообщает ядру Windows, поддерживает ли указанный исполняемый файл технологию Address Space Layout Randomization (ASLR) с высокой энтропией.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
/highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Этот параметр указывает, что 64-битный исполняемый файл или исполняемый файл, отмеченный параметром компилятора [/platform:anycpu](../../../csharp/language-reference/compiler-options/platform-compiler-option.md), поддерживает виртуальное адресное пространство с высокой энтропией. Этот параметр отключен по умолчанию. Чтобы включить его, используйте параметр **/highentropyva+** или **/highentropyva**.  
  
## <a name="remarks"></a>Примечания  
 Параметр **/highentropyva** позволяет совместимым версиям ядра Windows использовать более высокие степени энтропии во время смешивания структуры адресного пространства процесса в рамках ASLR. Использование более высоких степеней энтропии означает, что можно выделить больше адресов таким областям памяти, как стеки и кучи. Из-за этого сложнее подобрать расположение определенной области памяти.  
  
 Если указан параметр компилятора **/highentropyva**, целевой исполняемый файл и все модули, от которых он зависит, должны быть способны обработать значения указателя, размер которых превышает 4 гигабайта (ГБ), если они выполняются как 64-разрядный процесс.

