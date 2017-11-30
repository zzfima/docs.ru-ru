---
title: "-baseaddress (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /dllbase
helpviewer_keywords:
- baseaddress compiler option [C#]
- /baseaddress compiler option [C#]
- -baseaddress compiler option [C#]
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7cd3269754f783ab8b26683f5215aa81825673e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="baseaddress-c-compiler-options"></a>/baseaddress (параметры компилятора C#)
Параметр **/baseaddress** позволяет указать предпочтительный базовый адрес для загрузки библиотеки DLL. Дополнительные сведения о когда и почему следует использовать этот параметр, см. в разделе [блога Ларри Osterman](http://go.microsoft.com/fwlink/?LinkId=107044).  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
/baseaddress:address  
```  
  
## <a name="arguments"></a>Аргументы  
 `address`  
 Базовый адрес для библиотеки DLL. Этот адрес можно задать в десятичном, шестнадцатеричном или восьмеричном формате.  
  
## <a name="remarks"></a>Примечания  
 Базовый адрес по умолчанию для библиотеки DLL задается в среде CLR платформы .NET Framework.  
  
 Обратите внимание, что младшее слово этого адреса будет округляться. Например, значение 0x11110001 округляется до 0x11110000.  
  
 Чтобы завершить процесс подписи для библиотеки DLL, используйте файл SN. EXE с параметром -R.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Щелкните страницу свойств **Сборка**.  
  
3.  Нажмите кнопку **Дополнительно** .  
  
4.  Измените свойство **Базовый адрес DLL**.  
  
     Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=nameWithType>  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)  
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
