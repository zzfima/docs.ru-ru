---
title: "Чтение реестра и запись в него с использованием пространства имен Microsoft.Win32 (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "реестр, Visual Basic"
ms.assetid: 4a0dcce0-c27b-4199-baa8-ee4528da6a56
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Чтение реестра и запись в него с использованием пространства имен Microsoft.Win32 (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Хотя `My.Computer.Registry` должно хватать для удовлетворения основных потребностей при программировании с использованием реестра, в пространстве имен <xref:Microsoft.Win32> платформы [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] можно также использовать классы <xref:Microsoft.Win32.Registry> и <xref:Microsoft.Win32.RegistryKey>.  
  
## <a name="keys-in-the-registry-class"></a>Разделы в классе Registry  
 Класс <xref:Microsoft.Win32.Registry> предоставляет основные разделы реестра, которые можно использовать для доступа к подразделам и их значениям. Сами основные разделы доступны только для чтения. В таблице ниже перечислены и описаны семь разделов, предоставляемых классом <xref:Microsoft.Win32.Registry>.  
  
|**Key**|**Описание**|  
|-------------|---------------------|  
|<xref:Microsoft.Win32.Registry.ClassesRoot>|Определяет типы документов и свойства, связанные с этими типами.|  
|<xref:Microsoft.Win32.Registry.CurrentConfig>|Содержит сведения о конфигурации оборудования, не относящиеся к пользователю.|  
|<xref:Microsoft.Win32.Registry.CurrentUser>|Содержит сведения о текущих настройках пользователя, таких как переменные среды.|  
|<xref:Microsoft.Win32.Registry.DynData>|Содержит динамические данные реестра, например, используемые драйверами виртуальных устройств.|  
|<xref:Microsoft.Win32.Registry.LocalMachine>|Включает в себя пять подразделов (оборудование, SAM, безопасность, программное обеспечение и система), содержащих данные о конфигурации для локального компьютера.|  
|<xref:Microsoft.Win32.Registry.PerformanceData>|Содержит сведения о производительности для компонентов программного обеспечения.|  
|<xref:Microsoft.Win32.Registry.Users>|Содержит сведения о настройках пользователя по умолчанию.|  
  
> [!IMPORTANT]
>  Данные безопаснее записывать в раздел <xref:Microsoft.Win32.Registry.CurrentUser>, нежели в раздел <xref:Microsoft.Win32.Registry.LocalMachine>. Условие, которое обычно называют "захватом", возникает, если создаваемый вами раздел уже был создан другим, возможно вредоносным, процессом. Чтобы предотвратить это, используйте такой метод, как <xref:Microsoft.Win32.RegistryKey.GetValue%2A>, который возвращает `Nothing`, если раздел еще не существует.  
  
## <a name="reading-a-value-from-the-registry"></a>Чтение значения из реестра  
 В следующем коде показано, как считать строку из раздела HKEY_CURRENT_USER.  
  
 [!code-vb[VbResourceTasks#20](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/reading-from-and-writing_1.vb)]  
  
 Следующий код считывает, увеличивает, а затем записывает строку в раздел HKEY_CURRENT_USER.  
  
 [!code-vb[VbResourceTasks#21](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/reading-from-and-writing_2.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.SystemException>   
 <xref:System.ApplicationException>   
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>   
 [Оператор Try... Catch... Finally (Visual Basic)](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Чтение данных из реестра и запись в реестр (Visual Basic)](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)   
 [Безопасность и реестр](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)