---
title: "/baseaddress (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/dllbase"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "baseaddress compiler option [C#]"
  - "/baseaddress compiler option [C#]"
  - "-baseaddress compiler option [C#]"
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# /baseaddress (C# Compiler Options)
Параметр **\/baseaddress** позволяет указать предпочтительный базовый адрес для загрузки DLL.  Дополнительные сведения о том, когда и почему использовать этот параметр, см. в разделе [Улучшение времени запуска приложения](http://go.microsoft.com/fwlink/?LinkId=107043) и [Блог Ларри Остермана](http://go.microsoft.com/fwlink/?LinkId=107044).  
  
## Синтаксис  
  
```  
/baseaddress:address  
```  
  
## Аргументы  
 `address`  
 Базовый адрес DLL.  Адрес можно указать в виде десятичного, шестнадцатеричного или восьмеричного числа.  
  
## Заметки  
 Базовый адрес по умолчанию для библиотеки DLL задается в среде CLR платформы .NET Framework.  
  
 Имейте в виду, что младшее слово адреса округляется.  Например, если задать значение 0x11110001, оно будет округлено до 0x11110000.  
  
 Для подписывания библиотеки DLL используйте средство SN.EXE c параметром –R .  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Выберите страницу свойств **Построение**.  
  
3.  Нажмите кнопку **Дополнительно**.  
  
4.  Измените свойство **Базовый адрес DLL**.  
  
     Сведения об установке этого параметра компилятора программным способом см. в описании свойства <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.  
  
## См. также  
 <xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=fullName>   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)