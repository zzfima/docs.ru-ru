---
title: "-platform (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /platform
dev_langs:
- CSharp
helpviewer_keywords:
- platform compiler option [C#]
- -platform compiler option [C#]
- /platform compiler option [C#]
ms.assetid: c290ff5e-47f4-4a85-9bb3-9c2525b0be04
caps.latest.revision: 46
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
ms.openlocfilehash: 44d4cadbc45eb141ecb7a83345d2a7a834ce5299
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="platform-c-compiler-options"></a>/platform (параметры компилятора C#)
Указывает, в какой версии среды CLR может запускаться сборка.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
/platform:string  
```  
  
#### <a name="parameters"></a>Параметры  
 `string`  
 anycpu (по умолчанию), anycpu32bitpreferred, ARM, x64, x86 или Itanium.  
  
## <a name="remarks"></a>Примечания  
  
-   **anycpu** (по умолчанию) позволяет компилировать сборку для запуска на любой платформе. Если возможно, приложение выполняется как 64-разрядный процесс, а если доступен только 32-разрядный режим, переключается на него.  
  
-   **anycpu32bitpreferred** (по умолчанию) позволяет компилировать сборку для запуска на любой платформе. Приложение выполняется в 32-разрядном режиме в системах, поддерживающих и 64-разрядные, и 32-разрядные приложения. Можно задать этот параметр только для проектов, предназначенных для среды .NET Framework 4.5.  
  
-   **ARM** компилирует сборку для выполнения на компьютере с процессором Advanced RISC Machine (ARM).  
  
-   **x64** компилирует сборку для работы в 64-разрядной среде CLR на компьютере, поддерживающем набор инструкций x64 или AMD64.  
  
-   **x86** компилирует сборку для выполнения в 32-разрядной среде CLR, совместимой с архитектурой x86.  
  
-   **Itanium** компилирует сборку для выполнения в 64-разрядной среде CLR на компьютере с процессором Itanium.  
  
 В 64-разрядной ОС Windows:  
  
-   Сборки, скомпилированные с параметром **/platform:x86**, будут выполняться в 32-разрядной среде CLR с WOW64.  
  
-   Библиотека DLL, скомпилированная с использованием параметра **/platform:anycpu**, выполняется в той же среде CLR, в которую загружается процесс.  
  
-   Исполняемые файлы, скомпилированные с использованием параметра **/platform:anycpu**, выполняются в 64-разрядной среде CLR.  
  
-   Исполняемые файлы, скомпилированные с использованием параметра **/platform:anycpu32bitpreferred**, выполняются в 32-разрядной среде CLR.  
  
 Параметр **anycpu32bitpreferred** допустим только для исполняемых файлов (EXE-файлов), и для него необходима среда .NET Framework 4.5.  
  
 Дополнительные сведения о разработке приложений для запуска в 64-разрядной операционной системе Windows см. в разделе [64-разрядные приложения](https://msdn.microsoft.com/library/ms241064).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **свойств** для проекта.  
  
2.  Щелкните страницу свойств **Сборка**.  
  
3.  Измените значение свойства **Целевая платформа**, а для проектов, предназначенных для среды .NET Framework 4.5, установите или снимите флажок **Предпочитать 32-разрядную**.  
  
 Обратите внимание, что параметр **/platform** недоступен в среде разработки в Visual C# Express.  
  
 Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.  
  
## <a name="example"></a>Пример  
 В следующем примере показано использование параметра **/platform**, чтобы указать, что приложение должно выполняться в 64-разрядной среде CLR в 64-разрядной операционной системой Windows.  
  
```console  
csc /platform:anycpu filename.cs  
```  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C#](index.md)   
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)

