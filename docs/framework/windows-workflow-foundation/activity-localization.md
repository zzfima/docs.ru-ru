---
title: "Локализация действий | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8ee7bc16-e609-469a-a3e8-8062952e2676
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Локализация действий
Если приложения и компоненты рабочего процесса могут подлежать локализации для других языков и адаптации к особенностям других регионов, то в них следует использовать строки ресурсов, чтобы локализацию можно было провести без перекомпилирования.  
  
## Локализация действий  
 Как и при работе со всеми локализуемыми приложениями \(выпускаемыми в различных версиях для различных языков и различных региональных стандартов\), все отображаемые пользователю строки должны храниться в файле ресурсов, а не находиться в коде.Доступ к строкам можно осуществлять через объект <xref:System.Environment.GetResourceString>.При разработке компонента, распространяемого на различных языках, строки ресурсов также следует применять для сообщений проверки допустимости действий, определяемых пользователем данных отслеживания, сообщений трассировки и сообщений об ошибках.  
  
 В следующем примере демонстрируется применение файла ресурсов.  
  
#### Использование файлов ресурсов для локализованных строк  
  
1.  В [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] щелкните правой кнопкой мыши имя проекта в окне **Обозреватель решений**, выберите пункт **Добавить** и выберите пункт **Новый элемент...**.  
  
2.  Выберите вариант **Файл ресурсов** и назовите файл ErrorResources.resx.Нажмите кнопку **Добавить**.  
  
3.  Откройте файл ресурсов.Добавьте новую запись с **Именем** ErrorString и **Значением** «Действие недопустимо».  
  
4.  Добавьте к классу следующие инструкции `using`.  
  
    ```  
    using System.Reflection;  
    using System.Resources;  
  
    ```  
  
5.  Создайте в проекте диспетчер ресурсов.  
  
    ```  
    ResourceManager ErrorManager;  
    ...  
    ErrorManager = new ResourceManager("MyNamespace.ErrorResources", Assembly.GetExecutingAssembly());  
  
    ```  
  
6.  При необходимости строку можно получать из диспетчера ресурсов.  
  
    ```  
    String errorMessage = ErrorManager.GetString("ErrorString");  
  
    ```  
  
 В следующем образце кода показано использование локализованных строк в методе <xref:System.Activities.Activity.CacheMetadata%2A>.  
  
```  
       protected override void CacheMetadata(CodeActivityMetadata metadata)  
        {  
           .....  
          // rest of the code elided for brevity  
           .....  
            if (this.Value != null && this.To != null)  
            {  
                if (!TypeHelper.AreTypesCompatible(this.Value.ArgumentType, this.To.ArgumentType))  
                {  
//---------------------------------------------  
// ** SR.TypeMismatchForAssign will fetch the string from the resource manager **  
//---------------------------------------------  
                    metadata.AddValidationError(SR.TypeMismatchForAssign(  
                                this.Value.ArgumentType,  
                                this.To.ArgumentType,  
                                this.DisplayName));  
                }  
            }  
        }  
```