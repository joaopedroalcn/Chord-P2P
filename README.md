# João Pedro de Alcântara Lima

## Chord - Sistemas Distribuídos

Um protocolo Chord é implementado com base no Paper: “Chord – A Scalable Peer-to-Peer Lookup Service for Internet Applications”. Existem vários estágios cruciais para este algoritmo Chord. Na parte de junção, um recém-ingressado atualizará sua tabela de dedos primeiro e encontrará seu próprio sucessor e predecessor e, com base em sua própria tabela de dedos concluída, atualizará a tabela de dedos de outra invocando um método recursivo update_finger_table(s,i), que irá inicializar a i-ésima tabela de dedos com s no nó atual, este método é chamado ao receber uma mensagem exigindo que o nó atual faça isso. Depois disso, a atualização da chave acontecerá no nó recém-juntado e em seu sucessor, esse nó unido buscará as chaves menos do que seu próprio identificador de seu sucessor e, correspondentemente, essas chaves serão excluídas em seu sucessor. Na parte de localização, um nó pedirá ao próximo nó para encontrar a chave se ela não estiver em seu próprio conjunto de chaves. Se a chave estiver dentro do alcance da tabela de dedos do nó, o próximo nó será atribuído ao seu predecessor, caso contrário, o último nó da tabela de dedos. Para o comando crash, uma falha de nó será conhecida por outros nós pelo detector de pulsação e, sempre que um nó travar, todos os outros nós atualizarão sua tabela de dedos verificando se sua tabela contém esse nó, em caso afirmativo, atualize.
