<--------By Waqas Masood-------->

class Trie {
public:
    /** Initialize your data structure here. */
       Trie * root=NULL;
       unordered_map<char,Trie * > add;
       bool end_of_word=0;
    Trie() {
    //    map<char,Trie * > add;
      //  bool end_of_word=0;
    }
    
     //-------------INSERTING WORD------------
    /** Inserts a word into the trie. */
    void insert(string word) {
        
        Trie * ptr=root;
        
        //if we are inserting first character of first word
        if(root==NULL){
              Trie* node = new Trie();
            //  node.add[word[i]]=node;
               root=node;
               ptr=root;
              // ptr->end_of_word=0;   
           }
        
       
        for(int i=0 ; i<word.length(); i++){ 
            
            if(ptr->add.empty() || ptr->add.find(word[i])==ptr->add.end()){
                  Trie* node = new Trie();
                  ptr->add[word[i]]=node;
                //  node->end_of_word=0;   
                  ptr=node;
         
            }
          else{
                  ptr=ptr->add[word[i]];
              }
          
          }
        ptr->end_of_word=1; 
        
    
    }//end of insert()
    
    
     //-------------SEARCHING WORD------------
    /** Returns if the word is in the trie. */
    bool search(string word) {
        
           Trie * ptr=root;
        if(ptr==NULL)
            return 0;
        for(int i=0 ; i<word.length(); i++){ 
            
            if(ptr->add.find(word[i])==ptr->add.end()){
                  return 0;
            }
          else{
                  ptr=ptr->add[word[i]];
              }
          
          }
        return  ptr->end_of_word;
    
    }//end of search()
    
    //-------------SEARCHING PREFIX------------
    /** Returns if there is any word in the trie that starts with the given prefix. */
    bool startsWith(string prefix) {
         Trie * ptr=root;
           if(ptr==NULL)
            return 0;
        for(int i=0 ; i<prefix.length(); i++){ 
            
            if(ptr->add.find(prefix[i])==ptr->add.end()){
                  return 0;
            }
          else{
                  ptr=ptr->add[prefix[i]];
              }
          
          }
        return  1;
        
    }//end of startswith()
    
   //----------Deleting Words(this part copied from tushar roy, because felt lazy ,LOL)-----------
   
     void delete(string word) {
        delete(root, word, 0);
    }

    /**
     * Returns true if parent should delete the mapping
     */
     bool delete(Trie * current, string word, int index) {
     
        if (index == word.length()) {
            //when end of word is reached only delete if currrent.endOfWord is true.
            if (!current.endOfWord) {
                return false;
            }
            current.endOfWord = false;
            //if current has no other mapping then return true
            return current->add.size() == 0;
        }
        char ch = word[index];
        Trie * node = current->add[ch];
        if (node == null) {
            return false;
        }
        bool shouldDeleteCurrentNode = delete(node, word, index + 1);

        //if true is returned then delete the mapping of character and trienode reference from map.
        if (shouldDeleteCurrentNode) {
            current->add.erase(ch);
            //return true if no mappings are left in the map.
            return current->add.size() == 0;
        }
        return false;
        
     }// end of delete()
     
};
