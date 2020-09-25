# Recursos do Phan

Com Phan instalado, você precisa criar um .phan/config.php arquivo em seu projeto para dizer a Phan como analisar seu código-fonte. 
Uma vez configurado, você pode executá-lo via ./vendor/bin/phan

Phan é capaz de realizar os seguintes tipos de análise:

* Verifique se todos os métodos, funções, classes, características, interfaces, constantes, propriedades e variáveis ​​estão definidos e acessíveis.
* Verifique se há problemas de segurança de tipo e aridade nas chamadas de método / função / fechamento.
* Verifique a compatibilidade com versões anteriores do PHP7 / PHP5.
* Verifique se há recursos que não foram suportados em mais velhas PHP 7.x versões menores (Por exemplo object, void, iterable, ?T, [$x] = ...;, offsets cordas negativas, várias capturas de exceção, etc.)
* Verifique a sanidade com acessos de matriz.
* Verifique a segurança de tipo em operações binárias.
* Verifique se há valores de retorno válidos e seguros em métodos, funções e encerramentos.
* Verifique se há No-Ops em arrays, fechamentos, constantes, propriedades, variáveis, operadores unários e operadores binários.
* Verifique se há código não utilizado / morto / inacessível . (Passe --dead-code-detection)
* Verifique se há variáveis ​​e parâmetros não utilizados. (Passe --unused-variable-detection)
* Verifique se há condições redundantes ou impossíveis e conversões inúteis. (Passe --redundant-condition-detection)
* Verifique se há usedeclarações não utilizadas . Esses e alguns outros tipos de problemas podem ser corrigidos automaticamente com --automatic-fix.
* Verifique se há classes, funções e métodos sendo redefinidos.
* Verifique a integridade com a herança de classe (por exemplo, verifica a compatibilidade da assinatura do método). Phan também verifica se há classes / métodos finais sobrescritos, se métodos abstratos são implementados e se a interface implementada é realmente uma interface (e assim por diante).
* Suporta namespaces, traits e variadics.
* Suporta tipos de união .
* Suporta tipos genéricos (ou seja @template) .
* Suporta matrizes genéricas, tais como int[], UserObject[], array<int,UserObject>, etc ..
* Suporta formas de array como array{key:string,otherKey:?stdClass}, etc. (internamente e em tags PHPDoc) Isso também suporta a indicação de que os campos de uma forma de array são opcionais via array{requiredKey:string,optionalKey?:string}(útil para @param)
* Suporta anotações de tipo phpdoc .
* Suporta anotações de tipo phpdoc herdadas.
* Suporta verificar se as anotações de tipo phpdoc são uma forma restrita (por exemplo, subclasses / subtipos) das assinaturas de tipo real
* Suporta inferir tipos de declarações assert () e condicionais em elementos / loops if.
* Suporta @deprecatedanotações para classes, métodos e funções obsoletas
* Suporta @internalanotação para elementos (como uma constante, função, classe, constante de classe, propriedade ou método) como internos ao pacote no qual está definido.
* Suporta @suppress <ISSUE_TYPE>anotações para suprimir problemas .
* Suporta anotações mágicas de @property ( @property <union_type> <variable_name>)
* Suporta anotações mágicas de @method ( @method <union_type> <method_name>(<union_type> <param1_name>))
* Suporta class_aliasanotações (experimental, desativado por padrão)
* Suporta a indicação da classe à qual um fechamento será vinculado, via @phan-closure-scope( exemplo )
* Análise de suportes de fechos e tipos de retorno transmitido para arr* * ay_map, array_filtere outras funções de matriz internos.
* Oferece configuração extensiva para enfraquecer a análise para torná-la útil em grandes bases de código desleixadas
* Pode ser executado em muitos núcleos. (requer pcntl)
* A saída é emitida nos formatos de texto, checkstyle, json, pylint, csv ou codeclimate.
* Pode executar plug-ins de usuário na origem para verificações específicas do seu código . Phan inclui vários plug-ins que você pode desejar ativar para o seu projeto .
