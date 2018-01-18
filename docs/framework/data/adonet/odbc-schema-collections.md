---
title: "Коллекции схемы ODBC"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 45cfed80decc2336c5a2bacf24fd075c2b81c531
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="69784-102">Коллекции схемы ODBC</span><span class="sxs-lookup"><span data-stu-id="69784-102">ODBC Schema Collections</span></span>
<span data-ttu-id="69784-103">В данном разделе рассматривается поддержка коллекций схем для драйверов ODBC для Microsoft SQL Server, Oracle и Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="69784-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="69784-104">Драйвер ODBC для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="69784-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="69784-105">Драйвер ODBC для Microsoft SQL Server поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям схем.</span><span class="sxs-lookup"><span data-stu-id="69784-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="69784-106">Таблицы</span><span class="sxs-lookup"><span data-stu-id="69784-106">Tables</span></span>  
  
-   <span data-ttu-id="69784-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="69784-107">Indexes</span></span>  
  
-   <span data-ttu-id="69784-108">Столбцы</span><span class="sxs-lookup"><span data-stu-id="69784-108">Columns</span></span>  
  
-   <span data-ttu-id="69784-109">Процедуры</span><span class="sxs-lookup"><span data-stu-id="69784-109">Procedures</span></span>  
  
-   <span data-ttu-id="69784-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="69784-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="69784-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="69784-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="69784-112">Представления</span><span class="sxs-lookup"><span data-stu-id="69784-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="69784-113">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="69784-113">Tables and Views</span></span>  
  
|<span data-ttu-id="69784-114">ColumnName</span><span class="sxs-lookup"><span data-stu-id="69784-114">ColumnName</span></span>|<span data-ttu-id="69784-115">DataType</span><span class="sxs-lookup"><span data-stu-id="69784-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="69784-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="69784-116">TABLE_CAT</span></span>|<span data-ttu-id="69784-117">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-117">String</span></span>|  
|<span data-ttu-id="69784-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="69784-118">TABLE_SCHEM</span></span>|<span data-ttu-id="69784-119">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-119">String</span></span>|  
|<span data-ttu-id="69784-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-120">TABLE_NAME</span></span>|<span data-ttu-id="69784-121">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-121">String</span></span>|  
|<span data-ttu-id="69784-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-122">TABLE_TYPE</span></span>|<span data-ttu-id="69784-123">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-123">String</span></span>|  
|<span data-ttu-id="69784-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="69784-124">REMARKS</span></span>|<span data-ttu-id="69784-125">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="69784-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="69784-126">Indexes</span></span>  
  
|<span data-ttu-id="69784-127">ColumnName</span><span class="sxs-lookup"><span data-stu-id="69784-127">ColumnName</span></span>|<span data-ttu-id="69784-128">DataType</span><span class="sxs-lookup"><span data-stu-id="69784-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="69784-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="69784-129">TABLE_CAT</span></span>|<span data-ttu-id="69784-130">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-130">String</span></span>|  
|<span data-ttu-id="69784-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="69784-131">TABLE_SCHEM</span></span>|<span data-ttu-id="69784-132">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-132">String</span></span>|  
|<span data-ttu-id="69784-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-133">TABLE_NAME</span></span>|<span data-ttu-id="69784-134">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-134">String</span></span>|  
|<span data-ttu-id="69784-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="69784-135">NON_UNIQUE</span></span>|<span data-ttu-id="69784-136">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-136">Int16</span></span>|  
|<span data-ttu-id="69784-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="69784-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="69784-138">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-138">String</span></span>|  
|<span data-ttu-id="69784-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-139">INDEX_NAME</span></span>|<span data-ttu-id="69784-140">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-140">String</span></span>|  
|<span data-ttu-id="69784-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-141">TYPE</span></span>|<span data-ttu-id="69784-142">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-142">Int16</span></span>|  
|<span data-ttu-id="69784-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="69784-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="69784-144">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-144">Int16</span></span>|  
|<span data-ttu-id="69784-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-145">COLUMN_NAME</span></span>|<span data-ttu-id="69784-146">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-146">String</span></span>|  
|<span data-ttu-id="69784-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="69784-147">ASC_OR_DESC</span></span>|<span data-ttu-id="69784-148">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-148">String</span></span>|  
|<span data-ttu-id="69784-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="69784-149">CARDINATLITY</span></span>|<span data-ttu-id="69784-150">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-150">Int32</span></span>|  
|<span data-ttu-id="69784-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="69784-151">PAGES</span></span>|<span data-ttu-id="69784-152">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-152">Int32</span></span>|  
|<span data-ttu-id="69784-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="69784-153">FILTER_CONDITION</span></span>|<span data-ttu-id="69784-154">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-154">String</span></span>|  
|<span data-ttu-id="69784-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="69784-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="69784-156">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-156">String</span></span>|  
|<span data-ttu-id="69784-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="69784-158">Byte</span><span class="sxs-lookup"><span data-stu-id="69784-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="69784-159">Столбцы</span><span class="sxs-lookup"><span data-stu-id="69784-159">Columns</span></span>  
  
|<span data-ttu-id="69784-160">ColumnName</span><span class="sxs-lookup"><span data-stu-id="69784-160">ColumnName</span></span>|<span data-ttu-id="69784-161">DataType</span><span class="sxs-lookup"><span data-stu-id="69784-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="69784-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="69784-162">TABLE_CAT</span></span>|<span data-ttu-id="69784-163">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-163">String</span></span>|  
|<span data-ttu-id="69784-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="69784-164">TABLE_SCHEM</span></span>|<span data-ttu-id="69784-165">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-165">String</span></span>|  
|<span data-ttu-id="69784-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-166">TABLE_NAME</span></span>|<span data-ttu-id="69784-167">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-167">String</span></span>|  
|<span data-ttu-id="69784-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-168">COLUMN_NAME</span></span>|<span data-ttu-id="69784-169">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-169">String</span></span>|  
|<span data-ttu-id="69784-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-170">DATA_TYPE</span></span>|<span data-ttu-id="69784-171">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-171">Int16</span></span>|  
|<span data-ttu-id="69784-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-172">TYPE_NAME</span></span>|<span data-ttu-id="69784-173">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-173">String</span></span>|  
|<span data-ttu-id="69784-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="69784-174">COLUMN_SIZE</span></span>|<span data-ttu-id="69784-175">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-175">Int32</span></span>|  
|<span data-ttu-id="69784-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="69784-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="69784-177">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-177">Int32</span></span>|  
|<span data-ttu-id="69784-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="69784-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="69784-179">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-179">Int16</span></span>|  
|<span data-ttu-id="69784-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="69784-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="69784-181">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-181">Int16</span></span>|  
|<span data-ttu-id="69784-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="69784-182">NULLABLE</span></span>|<span data-ttu-id="69784-183">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-183">Int16</span></span>|  
|<span data-ttu-id="69784-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="69784-184">REMARKS</span></span>|<span data-ttu-id="69784-185">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-185">String</span></span>|  
|<span data-ttu-id="69784-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="69784-186">COLUMN_DEF</span></span>|<span data-ttu-id="69784-187">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-187">String</span></span>|  
|<span data-ttu-id="69784-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="69784-189">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-189">Int16</span></span>|  
|<span data-ttu-id="69784-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="69784-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="69784-191">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-191">Int16</span></span>|  
|<span data-ttu-id="69784-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="69784-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="69784-193">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-193">Int32</span></span>|  
|<span data-ttu-id="69784-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="69784-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="69784-195">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-195">Int32</span></span>|  
|<span data-ttu-id="69784-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="69784-196">IS_NULLABLE</span></span>|<span data-ttu-id="69784-197">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-197">String</span></span>|  
|<span data-ttu-id="69784-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="69784-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="69784-199">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-199">String</span></span>|  
|<span data-ttu-id="69784-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="69784-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="69784-201">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-201">String</span></span>|  
|<span data-ttu-id="69784-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="69784-203">Byte</span><span class="sxs-lookup"><span data-stu-id="69784-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="69784-204">Процедуры</span><span class="sxs-lookup"><span data-stu-id="69784-204">Procedures</span></span>  
  
|<span data-ttu-id="69784-205">ColumnName</span><span class="sxs-lookup"><span data-stu-id="69784-205">ColumnName</span></span>|<span data-ttu-id="69784-206">DataType</span><span class="sxs-lookup"><span data-stu-id="69784-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="69784-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="69784-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="69784-208">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-208">String</span></span>|  
|<span data-ttu-id="69784-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="69784-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="69784-210">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-210">String</span></span>|  
|<span data-ttu-id="69784-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="69784-212">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-212">String</span></span>|  
|<span data-ttu-id="69784-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="69784-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="69784-214">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-214">Int32</span></span>|  
|<span data-ttu-id="69784-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="69784-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="69784-216">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-216">Int32</span></span>|  
|<span data-ttu-id="69784-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="69784-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="69784-218">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-218">Int32</span></span>|  
|<span data-ttu-id="69784-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="69784-219">REMARKS</span></span>|<span data-ttu-id="69784-220">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-220">String</span></span>|  
|<span data-ttu-id="69784-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="69784-222">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="69784-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="69784-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="69784-224">ColumnName</span><span class="sxs-lookup"><span data-stu-id="69784-224">ColumnName</span></span>|<span data-ttu-id="69784-225">DataType</span><span class="sxs-lookup"><span data-stu-id="69784-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="69784-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="69784-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="69784-227">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-227">String</span></span>|  
|<span data-ttu-id="69784-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="69784-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="69784-229">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-229">String</span></span>|  
|<span data-ttu-id="69784-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="69784-231">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-231">String</span></span>|  
|<span data-ttu-id="69784-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-232">COLUMN_NAME</span></span>|<span data-ttu-id="69784-233">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-233">String</span></span>|  
|<span data-ttu-id="69784-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-234">COLUMN_TYPE</span></span>|<span data-ttu-id="69784-235">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-235">Int16</span></span>|  
|<span data-ttu-id="69784-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-236">DATA_TYPE</span></span>|<span data-ttu-id="69784-237">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-237">Int16</span></span>|  
|<span data-ttu-id="69784-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-238">TYPE_NAME</span></span>|<span data-ttu-id="69784-239">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-239">String</span></span>|  
|<span data-ttu-id="69784-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="69784-240">COLUMN_SIZE</span></span>|<span data-ttu-id="69784-241">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-241">Int32</span></span>|  
|<span data-ttu-id="69784-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="69784-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="69784-243">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-243">Int32</span></span>|  
|<span data-ttu-id="69784-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="69784-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="69784-245">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-245">Int16</span></span>|  
|<span data-ttu-id="69784-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="69784-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="69784-247">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-247">Int16</span></span>|  
|<span data-ttu-id="69784-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="69784-248">NULLABLE</span></span>|<span data-ttu-id="69784-249">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-249">Int16</span></span>|  
|<span data-ttu-id="69784-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="69784-250">REMARKS</span></span>|<span data-ttu-id="69784-251">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-251">String</span></span>|  
|<span data-ttu-id="69784-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="69784-252">COLUMN_DEF</span></span>|<span data-ttu-id="69784-253">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-253">String</span></span>|  
|<span data-ttu-id="69784-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="69784-255">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-255">Int16</span></span>|  
|<span data-ttu-id="69784-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="69784-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="69784-257">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-257">Int16</span></span>|  
|<span data-ttu-id="69784-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="69784-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="69784-259">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-259">Int32</span></span>|  
|<span data-ttu-id="69784-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="69784-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="69784-261">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-261">Int32</span></span>|  
|<span data-ttu-id="69784-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="69784-262">IS_NULLABLE</span></span>|<span data-ttu-id="69784-263">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-263">String</span></span>|  
|<span data-ttu-id="69784-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="69784-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="69784-265">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-265">String</span></span>|  
|<span data-ttu-id="69784-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="69784-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="69784-267">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-267">String</span></span>|  
|<span data-ttu-id="69784-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="69784-269">Byte</span><span class="sxs-lookup"><span data-stu-id="69784-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="69784-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="69784-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="69784-271">ColumnName</span><span class="sxs-lookup"><span data-stu-id="69784-271">ColumnName</span></span>|<span data-ttu-id="69784-272">DataType</span><span class="sxs-lookup"><span data-stu-id="69784-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="69784-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="69784-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="69784-274">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-274">String</span></span>|  
|<span data-ttu-id="69784-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="69784-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="69784-276">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-276">String</span></span>|  
|<span data-ttu-id="69784-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="69784-278">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-278">String</span></span>|  
|<span data-ttu-id="69784-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-279">COLUMN_NAME</span></span>|<span data-ttu-id="69784-280">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-280">String</span></span>|  
|<span data-ttu-id="69784-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-281">COLUMN_TYPE</span></span>|<span data-ttu-id="69784-282">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-282">Int16</span></span>|  
|<span data-ttu-id="69784-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-283">DATA_TYPE</span></span>|<span data-ttu-id="69784-284">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-284">Int16</span></span>|  
|<span data-ttu-id="69784-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-285">TYPE_NAME</span></span>|<span data-ttu-id="69784-286">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-286">String</span></span>|  
|<span data-ttu-id="69784-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="69784-287">COLUMN_SIZE</span></span>|<span data-ttu-id="69784-288">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-288">Int32</span></span>|  
|<span data-ttu-id="69784-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="69784-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="69784-290">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-290">Int32</span></span>|  
|<span data-ttu-id="69784-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="69784-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="69784-292">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-292">Int16</span></span>|  
|<span data-ttu-id="69784-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="69784-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="69784-294">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-294">Int16</span></span>|  
|<span data-ttu-id="69784-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="69784-295">NULLABLE</span></span>|<span data-ttu-id="69784-296">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-296">Int16</span></span>|  
|<span data-ttu-id="69784-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="69784-297">REMARKS</span></span>|<span data-ttu-id="69784-298">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-298">String</span></span>|  
|<span data-ttu-id="69784-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="69784-299">COLUMN_DEF</span></span>|<span data-ttu-id="69784-300">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-300">String</span></span>|  
|<span data-ttu-id="69784-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="69784-302">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-302">Int16</span></span>|  
|<span data-ttu-id="69784-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="69784-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="69784-304">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-304">Int16</span></span>|  
|<span data-ttu-id="69784-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="69784-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="69784-306">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-306">Int32</span></span>|  
|<span data-ttu-id="69784-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="69784-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="69784-308">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-308">Int32</span></span>|  
|<span data-ttu-id="69784-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="69784-309">IS_NULLABLE</span></span>|<span data-ttu-id="69784-310">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-310">String</span></span>|  
|<span data-ttu-id="69784-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="69784-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="69784-312">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-312">String</span></span>|  
|<span data-ttu-id="69784-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="69784-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="69784-314">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-314">String</span></span>|  
|<span data-ttu-id="69784-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="69784-316">Byte</span><span class="sxs-lookup"><span data-stu-id="69784-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="69784-317">Драйвер ODBC для Oracle (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="69784-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="69784-318">Microsoft SQL Server драйвер ODBC для Oracle поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям схем.</span><span class="sxs-lookup"><span data-stu-id="69784-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="69784-319">Таблицы</span><span class="sxs-lookup"><span data-stu-id="69784-319">Tables</span></span>  
  
-   <span data-ttu-id="69784-320">Столбцы</span><span class="sxs-lookup"><span data-stu-id="69784-320">Columns</span></span>  
  
-   <span data-ttu-id="69784-321">Процедуры</span><span class="sxs-lookup"><span data-stu-id="69784-321">Procedures</span></span>  
  
-   <span data-ttu-id="69784-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="69784-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="69784-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="69784-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="69784-324">Представления</span><span class="sxs-lookup"><span data-stu-id="69784-324">Views</span></span>  
  
-   <span data-ttu-id="69784-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="69784-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="69784-326">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="69784-326">Tables and Views</span></span>  
  
|<span data-ttu-id="69784-327">ColumnName</span><span class="sxs-lookup"><span data-stu-id="69784-327">ColumnName</span></span>|<span data-ttu-id="69784-328">DataType</span><span class="sxs-lookup"><span data-stu-id="69784-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="69784-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="69784-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="69784-330">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-330">String</span></span>|  
|<span data-ttu-id="69784-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="69784-331">TABLE_OWNER</span></span>|<span data-ttu-id="69784-332">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-332">String</span></span>|  
|<span data-ttu-id="69784-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-333">TABLE_NAME</span></span>|<span data-ttu-id="69784-334">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-334">String</span></span>|  
|<span data-ttu-id="69784-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-335">TABLE_TYPE</span></span>|<span data-ttu-id="69784-336">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-336">String</span></span>|  
|<span data-ttu-id="69784-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="69784-337">REMARKS</span></span>|<span data-ttu-id="69784-338">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="69784-339">Столбцы</span><span class="sxs-lookup"><span data-stu-id="69784-339">Columns</span></span>  
  
|<span data-ttu-id="69784-340">ColumnName</span><span class="sxs-lookup"><span data-stu-id="69784-340">ColumnName</span></span>|<span data-ttu-id="69784-341">DataType</span><span class="sxs-lookup"><span data-stu-id="69784-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="69784-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="69784-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="69784-343">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-343">String</span></span>|  
|<span data-ttu-id="69784-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="69784-344">TABLE_OWNER</span></span>|<span data-ttu-id="69784-345">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-345">String</span></span>|  
|<span data-ttu-id="69784-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-346">TABLE_NAME</span></span>|<span data-ttu-id="69784-347">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-347">String</span></span>|  
|<span data-ttu-id="69784-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-348">COLUMN_NAME</span></span>|<span data-ttu-id="69784-349">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-349">String</span></span>|  
|<span data-ttu-id="69784-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-350">DATA_TYPE</span></span>|<span data-ttu-id="69784-351">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-351">Int16</span></span>|  
|<span data-ttu-id="69784-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-352">TYPE_NAME</span></span>|<span data-ttu-id="69784-353">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-353">String</span></span>|  
|<span data-ttu-id="69784-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="69784-354">PRECISION</span></span>|<span data-ttu-id="69784-355">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-355">Int32</span></span>|  
|<span data-ttu-id="69784-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="69784-356">LENGTH</span></span>|<span data-ttu-id="69784-357">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-357">Int32</span></span>|  
|<span data-ttu-id="69784-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="69784-358">SCALE</span></span>|<span data-ttu-id="69784-359">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-359">Int16</span></span>|  
|<span data-ttu-id="69784-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="69784-360">RADIX</span></span>|<span data-ttu-id="69784-361">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-361">Int16</span></span>|  
|<span data-ttu-id="69784-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="69784-362">NULLABLE</span></span>|<span data-ttu-id="69784-363">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-363">Int16</span></span>|  
|<span data-ttu-id="69784-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="69784-364">REMARKS</span></span>|<span data-ttu-id="69784-365">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-365">String</span></span>|  
|<span data-ttu-id="69784-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="69784-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="69784-367">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="69784-368">Процедуры</span><span class="sxs-lookup"><span data-stu-id="69784-368">Procedures</span></span>  
  
|<span data-ttu-id="69784-369">ColumnName</span><span class="sxs-lookup"><span data-stu-id="69784-369">ColumnName</span></span>|<span data-ttu-id="69784-370">DataType</span><span class="sxs-lookup"><span data-stu-id="69784-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="69784-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="69784-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="69784-372">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-372">String</span></span>|  
|<span data-ttu-id="69784-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="69784-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="69784-374">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-374">String</span></span>|  
|<span data-ttu-id="69784-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="69784-376">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-376">String</span></span>|  
|<span data-ttu-id="69784-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="69784-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="69784-378">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-378">Int16</span></span>|  
|<span data-ttu-id="69784-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="69784-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="69784-380">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-380">Int16</span></span>|  
|<span data-ttu-id="69784-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="69784-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="69784-382">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-382">Int16</span></span>|  
|<span data-ttu-id="69784-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="69784-383">REMARKS</span></span>|<span data-ttu-id="69784-384">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-384">String</span></span>|  
|<span data-ttu-id="69784-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="69784-386">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="69784-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="69784-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="69784-388">ColumnName</span><span class="sxs-lookup"><span data-stu-id="69784-388">ColumnName</span></span>|<span data-ttu-id="69784-389">DataType</span><span class="sxs-lookup"><span data-stu-id="69784-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="69784-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="69784-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="69784-391">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-391">String</span></span>|  
|<span data-ttu-id="69784-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="69784-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="69784-393">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-393">String</span></span>|  
|<span data-ttu-id="69784-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="69784-395">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-395">String</span></span>|  
|<span data-ttu-id="69784-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-396">COLUMN_NAME</span></span>|<span data-ttu-id="69784-397">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-397">String</span></span>|  
|<span data-ttu-id="69784-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-398">COLUMN_TYPE</span></span>|<span data-ttu-id="69784-399">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-399">Int16</span></span>|  
|<span data-ttu-id="69784-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-400">DATA_TYPE</span></span>|<span data-ttu-id="69784-401">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-401">Int16</span></span>|  
|<span data-ttu-id="69784-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-402">TYPE_NAME</span></span>|<span data-ttu-id="69784-403">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-403">String</span></span>|  
|<span data-ttu-id="69784-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="69784-404">PRECISION</span></span>|<span data-ttu-id="69784-405">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-405">Int32</span></span>|  
|<span data-ttu-id="69784-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="69784-406">LENGTH</span></span>|<span data-ttu-id="69784-407">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-407">Int32</span></span>|  
|<span data-ttu-id="69784-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="69784-408">SCALE</span></span>|<span data-ttu-id="69784-409">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-409">Int16</span></span>|  
|<span data-ttu-id="69784-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="69784-410">RADIX</span></span>|<span data-ttu-id="69784-411">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-411">Int16</span></span>|  
|<span data-ttu-id="69784-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="69784-412">NULLABLE</span></span>|<span data-ttu-id="69784-413">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-413">Int16</span></span>|  
|<span data-ttu-id="69784-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="69784-414">REMARKS</span></span>|<span data-ttu-id="69784-415">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-415">String</span></span>|  
|<span data-ttu-id="69784-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="69784-416">OVERLOAD</span></span>|<span data-ttu-id="69784-417">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-417">Int32</span></span>|  
|<span data-ttu-id="69784-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="69784-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="69784-419">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="69784-420">Драйвер ODBC для Jet (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="69784-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="69784-421">Драйвер ODBC для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="69784-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="69784-422">Таблицы</span><span class="sxs-lookup"><span data-stu-id="69784-422">Tables</span></span>  
  
-   <span data-ttu-id="69784-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="69784-423">Indexes</span></span>  
  
-   <span data-ttu-id="69784-424">Столбцы</span><span class="sxs-lookup"><span data-stu-id="69784-424">Columns</span></span>  
  
-   <span data-ttu-id="69784-425">Процедуры</span><span class="sxs-lookup"><span data-stu-id="69784-425">Procedures</span></span>  
  
-   <span data-ttu-id="69784-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="69784-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="69784-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="69784-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="69784-428">Представления</span><span class="sxs-lookup"><span data-stu-id="69784-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="69784-429">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="69784-429">Tables and Views</span></span>  
  
|<span data-ttu-id="69784-430">ColumnName</span><span class="sxs-lookup"><span data-stu-id="69784-430">ColumnName</span></span>|<span data-ttu-id="69784-431">DataType</span><span class="sxs-lookup"><span data-stu-id="69784-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="69784-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="69784-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="69784-433">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-433">String</span></span>|  
|<span data-ttu-id="69784-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="69784-434">TABLE_OWNER</span></span>|<span data-ttu-id="69784-435">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-435">String</span></span>|  
|<span data-ttu-id="69784-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-436">TABLE_NAME</span></span>|<span data-ttu-id="69784-437">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-437">String</span></span>|  
|<span data-ttu-id="69784-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-438">TABLE_TYPE</span></span>|<span data-ttu-id="69784-439">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-439">String</span></span>|  
|<span data-ttu-id="69784-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="69784-440">REMARKS</span></span>|<span data-ttu-id="69784-441">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="69784-442">Столбцы</span><span class="sxs-lookup"><span data-stu-id="69784-442">Columns</span></span>  
  
|<span data-ttu-id="69784-443">ColumnName</span><span class="sxs-lookup"><span data-stu-id="69784-443">ColumnName</span></span>|<span data-ttu-id="69784-444">DataType</span><span class="sxs-lookup"><span data-stu-id="69784-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="69784-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="69784-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="69784-446">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-446">String</span></span>|  
|<span data-ttu-id="69784-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="69784-447">TABLE_OWNER</span></span>|<span data-ttu-id="69784-448">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-448">String</span></span>|  
|<span data-ttu-id="69784-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-449">TABLE_NAME</span></span>|<span data-ttu-id="69784-450">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-450">String</span></span>|  
|<span data-ttu-id="69784-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-451">COLUMN_NAME</span></span>|<span data-ttu-id="69784-452">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-452">String</span></span>|  
|<span data-ttu-id="69784-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-453">DATA_TYPE</span></span>|<span data-ttu-id="69784-454">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-454">Int16</span></span>|  
|<span data-ttu-id="69784-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-455">TYPE_NAME</span></span>|<span data-ttu-id="69784-456">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-456">String</span></span>|  
|<span data-ttu-id="69784-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="69784-457">PRECISION</span></span>|<span data-ttu-id="69784-458">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-458">Int32</span></span>|  
|<span data-ttu-id="69784-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="69784-459">LENGTH</span></span>|<span data-ttu-id="69784-460">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-460">Int32</span></span>|  
|<span data-ttu-id="69784-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="69784-461">SCALE</span></span>|<span data-ttu-id="69784-462">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-462">Int16</span></span>|  
|<span data-ttu-id="69784-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="69784-463">RADIX</span></span>|<span data-ttu-id="69784-464">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-464">Int16</span></span>|  
|<span data-ttu-id="69784-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="69784-465">NULLABLE</span></span>|<span data-ttu-id="69784-466">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-466">Int16</span></span>|  
|<span data-ttu-id="69784-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="69784-467">REMARKS</span></span>|<span data-ttu-id="69784-468">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-468">String</span></span>|  
|<span data-ttu-id="69784-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="69784-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="69784-470">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="69784-471">Процедуры</span><span class="sxs-lookup"><span data-stu-id="69784-471">Procedures</span></span>  
  
|<span data-ttu-id="69784-472">ColumnName</span><span class="sxs-lookup"><span data-stu-id="69784-472">ColumnName</span></span>|<span data-ttu-id="69784-473">DataType</span><span class="sxs-lookup"><span data-stu-id="69784-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="69784-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="69784-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="69784-475">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-475">String</span></span>|  
|<span data-ttu-id="69784-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="69784-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="69784-477">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-477">String</span></span>|  
|<span data-ttu-id="69784-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="69784-479">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-479">String</span></span>|  
|<span data-ttu-id="69784-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="69784-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="69784-481">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-481">Int16</span></span>|  
|<span data-ttu-id="69784-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="69784-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="69784-483">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-483">Int16</span></span>|  
|<span data-ttu-id="69784-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="69784-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="69784-485">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-485">Int16</span></span>|  
|<span data-ttu-id="69784-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="69784-486">REMARKS</span></span>|<span data-ttu-id="69784-487">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-487">String</span></span>|  
|<span data-ttu-id="69784-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="69784-489">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="69784-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="69784-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="69784-491">ColumnName</span><span class="sxs-lookup"><span data-stu-id="69784-491">ColumnName</span></span>|<span data-ttu-id="69784-492">DataType</span><span class="sxs-lookup"><span data-stu-id="69784-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="69784-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="69784-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="69784-494">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-494">String</span></span>|  
|<span data-ttu-id="69784-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="69784-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="69784-496">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-496">String</span></span>|  
|<span data-ttu-id="69784-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="69784-498">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-498">String</span></span>|  
|<span data-ttu-id="69784-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-499">COLUMN_NAME</span></span>|<span data-ttu-id="69784-500">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-500">String</span></span>|  
|<span data-ttu-id="69784-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-501">COLUMN_TYPE</span></span>|<span data-ttu-id="69784-502">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-502">Int16</span></span>|  
|<span data-ttu-id="69784-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-503">DATA_TYPE</span></span>|<span data-ttu-id="69784-504">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-504">Int16</span></span>|  
|<span data-ttu-id="69784-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-505">TYPE_NAME</span></span>|<span data-ttu-id="69784-506">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-506">String</span></span>|  
|<span data-ttu-id="69784-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="69784-507">PRECISION</span></span>|<span data-ttu-id="69784-508">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-508">Int32</span></span>|  
|<span data-ttu-id="69784-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="69784-509">LENGTH</span></span>|<span data-ttu-id="69784-510">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-510">Int32</span></span>|  
|<span data-ttu-id="69784-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="69784-511">SCALE</span></span>|<span data-ttu-id="69784-512">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-512">Int16</span></span>|  
|<span data-ttu-id="69784-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="69784-513">RADIX</span></span>|<span data-ttu-id="69784-514">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-514">Int16</span></span>|  
|<span data-ttu-id="69784-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="69784-515">NULLABLE</span></span>|<span data-ttu-id="69784-516">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-516">Int16</span></span>|  
|<span data-ttu-id="69784-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="69784-517">REMARKS</span></span>|<span data-ttu-id="69784-518">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-518">String</span></span>|  
|<span data-ttu-id="69784-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="69784-519">OVERLOAD</span></span>|<span data-ttu-id="69784-520">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-520">Int32</span></span>|  
|<span data-ttu-id="69784-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="69784-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="69784-522">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="69784-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="69784-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="69784-524">ColumnName</span><span class="sxs-lookup"><span data-stu-id="69784-524">ColumnName</span></span>|<span data-ttu-id="69784-525">DataType</span><span class="sxs-lookup"><span data-stu-id="69784-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="69784-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="69784-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="69784-527">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-527">String</span></span>|  
|<span data-ttu-id="69784-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="69784-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="69784-529">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-529">String</span></span>|  
|<span data-ttu-id="69784-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="69784-531">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-531">String</span></span>|  
|<span data-ttu-id="69784-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-532">COLUMN_NAME</span></span>|<span data-ttu-id="69784-533">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-533">String</span></span>|  
|<span data-ttu-id="69784-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-534">COLUMN_TYPE</span></span>|<span data-ttu-id="69784-535">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-535">Int16</span></span>|  
|<span data-ttu-id="69784-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-536">DATA_TYPE</span></span>|<span data-ttu-id="69784-537">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-537">Int16</span></span>|  
|<span data-ttu-id="69784-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="69784-538">TYPE_NAME</span></span>|<span data-ttu-id="69784-539">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-539">String</span></span>|  
|<span data-ttu-id="69784-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="69784-540">COLUMN_SIZE</span></span>|<span data-ttu-id="69784-541">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-541">Int32</span></span>|  
|<span data-ttu-id="69784-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="69784-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="69784-543">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-543">Int32</span></span>|  
|<span data-ttu-id="69784-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="69784-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="69784-545">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-545">Int16</span></span>|  
|<span data-ttu-id="69784-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="69784-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="69784-547">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-547">Int16</span></span>|  
|<span data-ttu-id="69784-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="69784-548">NULLABLE</span></span>|<span data-ttu-id="69784-549">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-549">Int16</span></span>|  
|<span data-ttu-id="69784-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="69784-550">REMARKS</span></span>|<span data-ttu-id="69784-551">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-551">String</span></span>|  
|<span data-ttu-id="69784-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="69784-552">COLUMN_DEF</span></span>|<span data-ttu-id="69784-553">Строковое</span><span class="sxs-lookup"><span data-stu-id="69784-553">String</span></span>|  
|<span data-ttu-id="69784-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="69784-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="69784-555">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-555">Int16</span></span>|  
|<span data-ttu-id="69784-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="69784-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="69784-557">Int16</span><span class="sxs-lookup"><span data-stu-id="69784-557">Int16</span></span>|  
|<span data-ttu-id="69784-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="69784-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="69784-559">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-559">Int32</span></span>|  
|<span data-ttu-id="69784-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="69784-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="69784-561">Int32</span><span class="sxs-lookup"><span data-stu-id="69784-561">Int32</span></span>|  
|<span data-ttu-id="69784-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="69784-562">IS_NULLABLE</span></span>|<span data-ttu-id="69784-563">String</span><span class="sxs-lookup"><span data-stu-id="69784-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="69784-564">См. также</span><span class="sxs-lookup"><span data-stu-id="69784-564">See Also</span></span>  
 [<span data-ttu-id="69784-565">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="69784-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
