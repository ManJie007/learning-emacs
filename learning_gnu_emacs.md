The Meta Key

The other modifier Emacs uses is the Meta key. Few keyboards have keys labeled Meta. Because of this, in previous editions of this book, we refused to talk about the Meta key and substituted Esc in all our instructions.

In this edition, we want you to learn where the Meta key is. Typically Meta keys are to the immediate left and right of the Space bar. On Linux and Windows keyboards, the Alt key is the Meta key. On Mac keyboards, the Apple key, often called Command is the Meta key by default.


Chapter I. Emacs Basics

A buffer can be in only one major mode at a time; to exit a major mode, you have to enter another one. 

In addition to major modes there are also minor modes. These define a particular aspect of Emacs's behavior and can be turned on and off within a major mode. 

All Emacs commands, even the simplest ones, have a full name; 
This tying of a command to a keystroke combination is called a key binding. Some commands have only full names, with no corresponding key binding.

To use commands with no keystrokes, type M-x, followed by the command's full name, and press Enter. 

How Emacs Chooses a Default Directory
The default directory is taken from the buffer that the cursor is currently in.

Opening a File 
M-x find-file RETURN or C-x C-f

If You Read the Wrong FIle
M-x find-alternate-file RETURN or C-x C-v

Minibuffer中Tab补全

Inserting and Appending Files
C-x i

Saving Files
C-x C-s

Writing File    The write-file command asks you to type a new filename in the minibuffer.
C-x C-w

Leaving Emacs
C-x C-c

Getting Help
C-h ?   gives you a list of options. 
C-h t   starts a tutorial that is an excellent introduction to Emacs.
C-h k   To get information about the meaning of a keystroke combination
C-h f   asks Emacs to describe a function (really just a command name, such as find-file). 
To make the *Help* buffer disappear, press C-x I


Keystrokes                                  Command name                        Action                                        
                                                                                                                                            
C-x C-f File → Open File                    find-file                           Find file and read it in a new buffer.       
C-x C-v                                     find-alternate-file                 Read an alternate file, replacing the one read with C-x C- f.
C-x i File → Insert File                    insert-file                         Insert file at cursor position.              
C-x C-s File → Save (current buffer)        save-buffer                         Save file.                                   
C-x C-w File → Save Buffer As               write-file                          Write buffer contents to file.               
C-x C-c File → Exit Emacs                   save-buffers-kill-emacs             Exit Emacs.                                  
C-h                                         help-command                        Enter the online help system.                
C-h f Help → Describe Function              describe-function                   Gives online help for a given command name.  
C-h k Help → Describe Key                   describe-key                        Gives online help for a given keystroke sequence.
C-h t Help → Emacs Tutorial                 help-with-tutorial                  Start the Emacs tutorial.                        
C-h i Help → Browse Manuals                 info-goto-emacs-commandnode         Start the Info documentation reader.            



Chapter 2. Editing

Refill mode is a minor mode that keeps paragraphs neat as you edit them. 
    It is not on by default. Look at the mode line. If the word Refill appears, you are in refill mode already. If not, you can turn it on for this buffer only by typing M-x refill-mode Enter. 
    If you decide that you don't like refill mode, type M-x refillmode Enter again. 

Keystrokes                                  Command name                        Action

(none) [1]                                  refill-mode                         Toggle refill mode, in which Emacs automatically reformats text.
(none) Options → Word Wrap in Text Modes    auto-fill-mode                      Toggle auto-fill mode, in which Emacs formats paragraphs as you type them.
M-q                                         fill-paragraph                      Reformat paragraph.
(none) Edit → Fill                          fill-region                         Reformat individual paragraphs within a region.

[1] Remember that (none) in the first column means that you type M-x followed by the command name in the second column, then press Enter to run the command. There are no default keystrokes. To use the refill-mode command, type M-x refill-mode Enter .

Moving 

Ctrl commands generally move in smaller units than their associated Meta commands.

Keystrokes                                  Command name                        Action                                                       
                                                                                
C-f                                         forward-char                        Move forward one character (right).
C-b                                         backward-char                       Move backward one character (left).
C-p                                         previous-line                       Move to previous line (up).
C-n                                         next-line                           Move to next line (down).
M-f                                         forward-word                        Move one word forward.
M-b                                         backward-word                       Move one word backward.
                                                                                
C-a                                         beginning-of-line                   Move to beginning of line.
C-e                                         end-of-line                         Move to end of line.
M-e                                         forward-sentence                    Move forward one sentence.
M-a                                         backward-sentence                   Move backward one sentence.
                                                                                
M-}                                         forward-paragraph                   Move forward one paragraph.
M-{                                         backward- paragraph                 Move backward one paragraph.
                                                                                
C-v                                         scroll-up                           Move forward one screen.
M-v                                         scroll-down                         Move backward one screen.
                                                                                
C-x ]                                       forward-page                        Move forward one page.
C-x [                                       backward-page                       Move backward one page.
M-<                                         beginning-of-buffer                 Move to beginning of file.
M->                                         end-of-buffer                       Move to end of file.
                                                                                
(none)                                      goto-line                           Go to line n of file.
(none)                                      Roto-char                           Go to character n of file.
                                                                                
C-l                                         recenter                            Redraw screen with current line in the center.
                                                                                
M-n                                         digit-argument                      Repeat the next command n times.
C-u n                                       universal-argument                  Repeat the next command n times (four times if you omit 1）.

Deleting Text

The Kill Ring   Text that has been killed is not gone forever but is hidden in an area called the kill ring. The kill ring is an internal storage area where Emacs puts things you've copied or deleted.
                About the only thing that Emacs doesn't save in the kill ring is single characters, deleted with Del or C-d. (If you need to, you can get this type of deletion back using the undo command, bound to both C- _ and C-x u.)

Keystrokes                                  Command name                        Action                                    
                                                                                
C-d                                         delete-char                         Delete character under cursor.            
Del                                         delete-backward-char                Delete previous character.              
                                                                                
M-d                                         kill-word                           Delete next word.                         
M-Del                                       backward-kill-word                  Delete previous word.                     
                                                                                                                        
C-k                                         kill-line                           Delete from cursor to end of line.        
M-k                                         kill-sentence                       Delete next sentence.                     
C-x Del                                     backward-kill-sentence              Delete previous sentence.                 
                                                                                                                        
C-y                                         yank                                Restore what you've deleted.              
                                                                                                                        
C-w Edit → Cut                              kill-region                         Delete a marked region (see next section).
                                                                                                                        
(none)                                      kill-paragraph                      Delete next paragraph.                    
(none)                                      backward-kill- paragraph            Delete previous paragraph.                

Recovering Earlier Deletions

Keystroke                                   Action

C-y                                         This was the most recent deletion.
M-y                                         This was the second-last deletion.
M-y                                         This was the third-last deletion.
M-y                                         This was the fourth-last deletion.

You can keep on typing M-y, retrieving successively more ancient deletions, until you reach the end of the kill ring (at which point it cycles back to the most recently killed text; that's why it's called a ring).

Thirty deletions by default is a nice size—far more generous than most programs offer. But you can enlarge or reduce the size of the kill ring if you wish, using a variable called kill-ring-max. To experiment, give the command: M-x set-variable Enter kill-ring-max Enter new-value Enter (where new-value is a number).

Selecting and Pasting

Keystrokes                                   Command name                       Action                                                       
                                                                                
C-@ or C- Space                              set-mark-command                   Mark the beginning (or end) of a region.         
C-x C-x                                      exchange-point-andmark             Exchange location of cursor and mark.           
                                                                                            
C-w                                          kill-region                        Delete the region.          
C-y                                          yank                               Paste most recently killed or copied text.       
M-w                                          kill-ring-save                     Copy the region (so it can be pasted with C- (y).
                                                                                            
M-h                                          mark-paragraph                     Mark paragraph.         
C-x C-P                                      mark-page                          Mark page.          
C-x h                                        mark-whole-buffer                  Mark buffer.            
                                                                                            
M-y                                         yank-pop                            After C-y , pastes earlier deletion.            

Placing Text on the Clipboard

                        Linux       Windows     Mac OS X graphical      Mac OS X terminal
Sends to clipboard?     no          yes         yes                     no [4]
Sends to kill ring?     yes         yes         yes                     no

[4] You can make this happen if you highlight the text and then press xxxMacSymxxx -C. Simply highlighting the text doesn't copy it to the clipboard.

To send text to the clipboard on Linux, select it with the mouse (or mark it as a region), then click on the cut or copy toolbar icon or menu option. 

Retrieving Text from the Clipboard

                            Linux       Windows     Mac OS X graphical      Mac OS X terminal
C-y pastes?                 yes         yes         yes                     no[5]
Toolbar paste icon pastes?  yes         yes         no                      no
Edit → Paste option pastes? yes         yes         no                      no
Middle mouse button pastes? yes         yes         yes                     no
M-x clipboard-yank pastes?  yes         yes         yes                     no

[5] xxxMacSymxxx-v passtes from the clipboard.

 
Keystrokes                                  Command name                        Action                                                         
                                                                                                                                               
(none)                                      clipboard-kill-region               Cut region and place both in kill ring and on system clipboard.
(none)                                      clipboard-yank                      Paste text from clipboard.                                     
(none)                                      clipboard-kill-ringsave             Copy text to clipboard.                                        


Fixing Transpositions

Keystroke                                    Command name                         Action                      
                                                                                  
C-t                                         transpose-chars                       Transpose two letters.
M-t                                         transpose-words                       Transpose two words.
C-x C-t                                     transpose-lines                       Transpose two lines.
(none)                                      transpose-sentences                   Transpose two sentences.
(none)                                      transpose-paragraphs                  Transpose two paragraphs.


Changing Capitalization

Keystrokes                                  Command name                            Action
                                                                                    
M-c                                         capitalize-word                         Capitalize first letter of word.
M-u                                         upcase-word                             Uppercase word.
M-l                                         downcase-word                           Lowercase word.
                                                                                    
Meta-M-c                                    negative-argument; capitalizeword       Capitalize previous word.
Meta-M-u                                    negative-argument; upcase-word          Uppercase previous word.
Meta-M-l                                    negative-argument; downcaseword         Lowercase previous word.


Overwrite Mode

Keystrokes                                  Command name                            Action
                                                                                    
Insert                                      overwrite-mode                          enter overwrite mode.            

You can turn off overwrite mode by typing M-x overwrite-mode Enter again. Using Emacs's command completion, simply type M-x ov and press Enter. This is enough of a unique string to tell Emacs you want to toggle overwrite mode. 

Undoing Changes

Keystrokes                                  Command name                            Action
                                                                                    
C-g                                         keyboard-quit                           Abort current command.
C-x u                                       advertised-undo [8]                     Undo last edit (can be done repeatedly).
C-_ Edit → Undo                             undo                                    Undo last edit (can be done repeatedly).
(none)                                      revert-buffer                           Restore buffer to the state it was in when the file was last saved (or autosaved).

[8] There is no real difference between undo and advertised-undo. They work the same way.

Recovering Lost Changes

To recover text from an auto-save file, type M-x recover-file Enter. 

When does Emacs create auto-save files? Emacs creates an auto-save file every few hundred keystrokes or if Emacs is terminated abnormally.! You can change the frequency with which Emacs creates auto-save files by changing the variable auto-save-interval. By default, Emacs creates an auto-save file every 300 keystrokes.

There's one more important fact to know about Emacs and auto-save files. If you delete a large portion of a file, Emacs stops auto-saving the file and displays a message telling you so. To make Emacs start auto-saving again, save the file with C-x C-s or type M-I M-x auto-save Enter (that's the number 1).

Making Emacs Work the Way You Want
1.Enter Emacs (if you're not already there).
2.Type C-x C-f ~/.emacs Enter.
3. Type the line to be added exactly as shown in this book and press Enter.
4. Press C-x C-s to save the .emacs file.
5. Press C-x C-c to exit Emacs.
6. Restart Emacs to have the line take effect.

Hiding the Toolbar
```
(custom-set-variables
;;custom-set-variables was added by Custom.
;;If you edit it by hand, you could mess it up, so be careful.
;;Your init file should contain only one such instance.
;;If there is more than one, they won't work right.
'(tool-bar-mode nil nil (tool-bar)))

(custom-set-faces
;;custom-set-faces was added by Custom.
;;If you edit it by hand, you could mess it up, so be careful.
;;Your init file should contain only one such instance.
;;If there is more than one, they won't work right.
)
```

Turning On CUA Mode for C-x, C-c, and C-v to Cut, Copy, and Paste
```
(custom-set-variables
;;custom-set-variables was added by Custom.
;;If you edit it by hand, you could mess it up, so be careful.
;;Your init file should contain only one such instance.
;;If there is more than one, they won't work right.
'(cua-mode t nil (cua-base))
'(tool-bar-mode nil nil (tool-bar)))

(custom-set-faces
;;custom-set-faces was added by Custom.
;;If you edit it by hand, you could mess it up, so be careful.
;;Your init file should contain only one such instance.
;;If there is more than one, they won't work right.
)
```

Turning On Text Mode and Auto-Fill Mode Automatically
```
(setq default-major-mode 'text-mode)
(add-hook 'text-mode-hook 'turn-on-auto-fill)

(add-hook 'text-mode-hook (lambda () (refill-mode I)))
```

Remapping Keys

```
(define-key global-map "\C-x\C-u" 'undo)
```

Chapter 3. Search and Replace

Incremental Search
Keystrokes                                                          Command name                            Action                                                                                                             
                                                                                                                                                                                                                            
C-s Edit → Search → Incremental Search → Forward String             isearch-forward                         Start incremental search forward; follow by search string. Also, find next occurrence (forward) of search string.  
C-r Edit → Search → Incremental Search → Backward String            isearch-backward                        Start incremental search backward; follow by search string. Also, find next occurrence (backward) of search string.
                                                                                                                                                                                                                  
Enter                                                               isearch-exit                            In an incremental search, exit the search.                                                                         
                                                                                                                                                                                                                            
C-g                                                                 keyboard-quit                           In an incremental search, cancel the search.                                                                       
                                                                                                                                                                                                                            
Del                                                                 isearch-delete- char                    In an incremental search, delete character from search string.                                                     
C-s C-w                                                             isearch-yank-word                       Start an incremental search with the word the cursor is on as the search string.                                   
C-s C-y                                                             isearch-yank-line                       Start an incremental search with the text from the cursor position to the end of the line as the search string.    
C-s M-y                                                             isearch-yank-kill                       Start an incremental search with text from the kill ring as the search string.                                     
                                                                                                                                                                                                                            
C-s C-s                                                             isearch-repeat- forward                 Repeat previous search.                                                                                            
C-г С-г                                                             isearch-repeat- backward                Repeat previous search backward.                                                                                   

Simple Searches

Keystrokes                                                          Action                                
                                                                    
C-s Enter searchstring Enter Edit - Search - String Forward         Start nonincremental search forward.  
C-s                                                                 Repeat search forward.               
C-r Enter searchstrin g Enter Edit - Search - String                Start nonincremental search backward. 
C-r                                                                 Repeat search backward.               

Word Search
To do a word search, type C-s Enter C-w (for word-search-forward). The prompt Word search appears in the minibuffer. (Don't be put off by the prompts that appear along the way: you'll see an I-search prompt after typing C-s and a Search prompt after pressing Enter. Ignore these.) Type the search string and press Enter.

Emacs searches for the given string. To do a word search backwards, type C-r Enter C-w instead. 

Simple Search and Replace Operations

Type M-x replace-string Enter, then type the search string and press Enter.Now type the replacement string and press Enter again. Emacs replaces all occurrences in the file from the cursor position onward. 
If you want to search and replace throughout the file, press M-< to go to the beginning of the file before typing this command. Here's a quick example of using replace-string.

Query-Replace

To use query-replace, go to the beginning of the buffer using M-< and then type M-%.
Type the search string and press Enter.
Type the replacement string and press Enter.
Type the replacement string and press Enter.

Keystrokes                  Action                                                                                  
                                                                                                                
Space or y                  Replace searchstring with newstring and go to the next instance of the string.             
Del or n                    Don't replace; move to next instance.                                                       
.                           Replace the current instance and quit.                                         
,                           Replace and let me see the result before moving on. (Press Space or y to move on.) 
!                           Replace all the rest and don't ask.
^                           Back up to the previous instance.                                                   
Enter or q                  Exit query-replace.                                                 
E                           Modify the replacement string.                                                          
C-r                         Enter a recursive edit (discussed in detail later).                                        
C-w                         Delete this instance and enter a recursive edit (so you can make a custom replacement).              
C-M-c                       Exit recursive edit and resume query-replace.                                                        
C-]                         Exit recursive edit and exit query-replace.                                                     

Repeating Query-Replaces (and Other Complex Commands)
Pressing C-x Esc Esc. The last complex command you typed appears. If it's not the one you want, type M-p to see the previous command (do this as many times as necessary; M-n goes to the next command).

Recursive Editing

Are Emacs Searches Case-Sensitive?
By default, Emacs searches are not case-sensitive.
The variable case-fold-search determines whether searches are case-sensitive.
Likewise, if you don't want Emacs to adjust the case of your replacement strings, you can set the variable case-replace. 
Type M-x set-variable Enter variable-name Enter value Enter.
You can set the value for option permanently by selecting Save Options from the Options menu or by adding this line to your emacs file:
```
(setq-default case-fold-search nil) ; require exact matches
(setq-default case-replace nil) ; never change case when replacing
```

Regular Expressions for Search and Replacement Operations

Character(s)    Match
^               Matches the beginning of a line.
$               Matches the end of a line.
.               Matches any single character (like ? in filenames).
.*              Matches any group of zero or more characters (. matches any character and * matches zero or more of the previous character).
\<              Matches the beginning of a word.
\>              Matches the end of a word.
[]              Matches any character specified within the brackets; for example, [a-z] matches any alphabetic character.
\s,\S           Matches any whitespace character: space, a newline, a tab, a carriage return, a formfeed, or a backspace; IS matches any character except whitespace.
\d,\D           Matches any single digit, 0-9; \D matches any character but a digit.
\w,\W           Matches any "word" character (upper- and lowercase letters, digits, and the underscore character); \W matches any character but these.

Keystrokes                                                                                          Command name                            Action                                                                             
                                                                                                                                                            
C-M-s Enter Edit → Search → Regexp Forward                                                          re-search-forward                       Search for a regular expression forward.                
C-M-r Enter Edit → Search → Regexp Backwards                                                        re-search-backward                      Search for a regular expression backward.               
C-M-s Edit → Search → Incremental Search → Forward Regexp                                           isearch-forward-regexp                  Search incrementally forward for a regular expression.              
C-M-r Edit - Search → Incremental Search - Backward Regexp                                          isearch-backward-regexp                 Search incrementally backward for a regular expression.             
C-M-% Edit → Replace → Replace Regexp                                                               query-replace-regexp                    Query-replace a regular expression.             
(none )                                                                                             replace-regexp                          Globally replace a regular expression unconditionally (use with caution).


Checking Spelling Using Ispell
Emacs includes two spell-checking interfaces: to the Unix spell checker, spell, and to Ispell, which many people, including us, prefer. We say "interfaces" because Emacs does not include the executables for either of these spell-checkers. 
A further enhancement to Ispell is Flyspell, a command that highlights misspelled words on the fly. If you have Ispell installed, you'll have Flyspell support as well.

 In this case, we have a properly spelled name, so press i to ask Ispell to insert it into your private dictionary, which is kept in a file called ispell < language > in your home directory,"' where language is the language you are using (English by default). If this file doesn't exist, Ispell creates it without complaint and later asks you if you want to save it. To insert the word in the dictionary in lowercase, press u and Ispell lowercases the word and then puts it into your dictionary. Of course, because this is a proper name, we insert it as it appears in the passage.

To replace a word yourself, press r. After you type the corrected word, Ispell replaces it. If you press R instead, Ispell starts a query-replace through which you can correct all cases of the misspelling in this buffer.

Instead of replacing the word, you may simply want Ispell to skip over it. To skip this occurrence of a misspelled word, press Space. To ignore a misspelled word for the rest of the session for all buffers, press a (for accept). Uppercase A has one subtle difference: it tells Ispell to accept the word for this session but only in this buffer.

If you can see that something more complicated is wrong, you can start a recursive edit by typing C-r. Fix the error and type C-M-c to exit the recursive edit and resume Ispell. (You may recall that we discussed recursive editing earlier in this chapter.)

We want to replace all occurrences of the misspelled word, so we'll type!, which, as you might recall, means "replace them all without asking."

Checking a Single Word
To check the word the cursor is on, type M-$ (for ispell-word).

Completing a Word
Type M-Tab (for ispell-complete-word) and you get a list of choices. After typing occur, you use this command to find out the answer.

Spellchecking on the Fly with Flyspell
To check text as you type, enter Flyspell mode by typing M-x flyspell-mode Enter.
An alternative to Flyspell mode is Flyspell prog mode. In this mode, designed for programmers, Emacs highlights misspellings only in comments or strings. To enter it, type M- flyspell-prog-mode Enter.
To check existing text, you run M-x flyspell-buffer Enter.

To enter flyspell mode automatically, add this line to your .emacs file:
```
(setq-default flyspell-mode t)
```

Keystrokes                                                                  Command name                        Action                                                                                                            
                                                                                                                                
M-$ Tools → Spell Checking - Spell-Check Word                               ispell-word                         Check the word the cursor is on or the word following the cursor.               
(none) Tools → Spell Checking - Spell-Check Region                          ispell-region                       Check spelling of the region.               
(none) Tools → Spell Checking - Spell-Check Buffer                          ispell-buffer                       Check spelling of the buffer.               
(none) Tools → Spell Checking - Spell-Check Message                         ispell-message                      Check spelling of the body of a mail message.               
(none) Tools → Spell Checking → Spell-Check Comments                        ispell-comments-andstrings          Check spelling of comments and strings in a program.                
C-u M-S Tools → Spell Checking → Continue Spell- Checking                   ispell-continue                     Resume Ispell; it works only if stopped Ispell with C-g.                
(none )                                                                     ispell-kill-ispell                  Kill the Ispell process, which continues to run in the background after it is invoked.              
M-Tab Tools → Spell Checking → Complete Word                                ispell-complete-word                In text mode, list possible completions for the current word.               
(none) Tools → Spell Checking → Automatic Spell- Checking (Flyspell)        flyspell-mode                       Enter the Flyspell minor mode, in which incorrectly spelled words are highlighted.                   
(none)                                                                      flyspell-buffer                     Spell-check the current buffer, underlining all misspelled words. Use middle mouse button to correct.

Word Abbreviations
Dynamic Abbreviations
M-/ (for dabbrev-expand)    Interesting was not the word we were hoping for; it's invertebrates we wanted. Without moving the cursor, type M-/ again.

Word Abbreviation Mode
Trying word abbreviations for one session
To define word abbreviations for this buffer and session:
1. Enter word abbreviation mode by typing M-x abbrev-mode Enter. Abbrev appears on the mode line.
For a global abbreviation, type the abbreviation you want to use and type C-x a i g or C-x a - (for addinverse-global). (For a local abbreviation, type C-x a i 1 for add-inverse-local instead.) Emacs then asks you for the expansion.
2. Type the definition for the abbreviation and press Enter. Emacs then expands the abbreviation and will do so each time you type it followed by a space or punctuation mark.
3. When you exit Emacs. it asks if you want to save the abbreviations in abbrev_defs. Type y if you want to save them.
4. The abbreviations you've defined will work only in buffers where you enter abbrev mode.

Making word abbreviations part of your startup
1. Add these lines to your .emacs file:
```
(setq-default abbrev-mode t)
(read-abbrev-file "~/.abbrev_defs")
(setq save-abbrevs t)
```
2. Save the .emacs file and reenter Emacs. Abbrev appears on the mode line. You may get an error message saying Emacs can't load your abbrev file (understandable if you haven't created the file yet). Ignore this error message; it won't happen again.
3. Type an abbreviation and type C-x a i g or C-x a - following the abbreviation. These commands create a global abbreviation; if you want to create a local abbreviation instead, type C-x a i l. Emacs asks you for the expansion.
4. Type the definition for the abbreviation and press Enter. Emacs expands the abbreviation and will do so each time you type it followed by a space or punctuation mark. You can define as many abbreviations as you want to by repeating Steps 3 and 4.
5. Type C-x C-c to exit Emacs. Emacs asks if you want to save the abbreviations in abbrev_defs.
6. Type y to save your abbreviations.

Deleting a word abbreviation
You can edit the word abbreviation list by typing M-x edit-abbrevs Enter. You can see (but not edit) the list by typing M-x list-abbrevs Enter.
After the list is displayed, use C-k (or any other editing commands) to delete the abbreviations you don't want to use. 
To delete any abbreviation, delete the line for that abbreviation and save the file by typing M-x writeabbrev-file. 
You can move back to the buffer you were editing before by typing C-x b (a command for working with multiple buffers, discussed in Chapter 4).

Disabling word abbreviations
You can get rid of word abbreviations completely in one of two ways. 
First, you can type M-x kill-allabbrevs Enter. This command disables word abbreviations for the current session.
Second, you can delete the file the abbreviations are in. If you made word abbreviations part of your startup, delete the read-abbrev-file line from your .emacs file.

Abbreviations and capitalization
Abbreviation    Definition      You type:   Expands to:     Because :
                                                            
lc              lamb chop       lc          lamb chop       lc is lowercase, so lamb chop is lowercase.
lc              lamb chop       Lc          Lamb chop       There's one capital in Lc , so Lamb is capitalized.
lc              lamb chop       lC          Lamb chop       There's one capital in lC , so Lamb is capitalized.
lc              lamb chop       LC          Lamb Chop       LC is all capitals, so both words are capitalized.
lc              Lamb Chop       lc          Lamb Chop       Capitals in the definition are always unchanged.
lc              Lamb Chop       LC          Lamb Chop       Capitals in the definition are always unchanged.

Keystrokes              Command name                    Action
                                                        
M-/                     dabbrev-expand                  Complete this word based on the neare st word that starts with this string (press M-/ again if that's not the word you want).
(none)                  abbrev-mode                     Enter (or exit) word abbreviation mode.
C-x a - or C-x a i g    inverse-add-globalabbrev        After typing the global abbreviation,  type the definition.
C-x a il                inverse-add-modeabbrev          After typing the local abbreviation, type the definition.
(none)                  unexpand-abbrev                 Undo the last word abbreviation.
(none)                  write-abbrev-file               Write the word abbreviation file.
(none)                  edit-abbrevs                    Edit the word abbreviations.
(none)                  list-abbrevs                    View the word abbreviations.
(none)                  kill-all-abbrevs                Kill abbreviations for this session.

Chapter 4. Using Buffers, Windows, and Frames

From now on, when we say frame, we mean a separate GUI window. 
When we say window, we mean a portion of the current Emacs display. 

How do you know how many buffers are active in Emacs and what they are? 
There are three ways: 
the buffer list (which appears in a window when you type C-x C-b), 
the Buffers menu (which lists active buffers and commands for navigating them), 
and the Buffer pop-up menu (accessed by holding down Ctrl and clicking the left mouse button, which lists buffers by mode).

When you start Emacs, it generates two buffers:

*Messages* is a buffer where Emacs accumulates messages from its startup and from the minibuffer.
*scratch* is just what it sounds like: a temporary scratchpad where you can type. It won't be saved unless you explicitly write it to a file using C-x C-w.
If you ask for help, you'll also have a *Help* buffer.

Switching Buffers

If you type C-x b followed by:          Emacs :
                                        
A new buffer name                       Creates a new buffer that isn't connected with a file and moves there.
The name of an existing buffer          Moves you to the buffer (it doesn't matter whether the buffer is connected with a file or not).记得可以Tab补全.

Deleting Buffers

To delete a buffer, type C-x k (for kill-buffer).
Type M-x kill-some-buffers to weed out unneeded buffers this way.

Working with Windows
    Creating Horizontal Windows
        The most commonly used window command is C-x 2 (for split-window-vertically).

    A number of the "other window" commands are just the ordinary command with a 4 inserted in it. For example, to find a file in another window, type C-x 4 f.They save you a step: you need not move to the window, give a command, and move back.

    Once you've got multiple windows open, it's helpful to be able to scroll them without moving there. To scroll the other window, type C-M-v.

Moving Between Windows
C-x o (o stands for other in this command).

Getting Rid of Windows
Deleting a window only means that it isn't displayed anymore; it doesn't delete any of the information or any of your unsaved changes. The underlying buffer is still there, and you can switch to it using C-x b. 

To delete the window you're in, type C-x 0 (zero). 
If you want to delete all windows but the one you're working on, type C-x 1 (one), meaning "make this my one and only window."
You can also delete all windows on a certain buffer by typing: M-x delete-windows-on Enter buffername Enter.

Working with Frames
Creating a New Frame
    To open a new frame, type C-x 5 2 (for make-frame). Emacs makes a new frame containing the current buffer and puts it on top of the current frame.

If your new frame completely overlaps your current frame, you may need to size the new frame to tell them apart. For a more convenient solution, add these lines to your emacs file:
```
(setq initial-frame-alist '((top . 10) (left. 30)
                (width . 90) (height . 50)))
(setq default-frame-alist '(width . 80) (height . 45)))
```

To move to a buffer and put it in a new frame, type C-x 5 b. You might have guessed that one.

Moving Between Frames
You can use the mouse to select a frame or press C-x 5 o to go to another frame.

Deleting and Minimizing Frames
To get rid of a frame, press C-x 5 0. 
    Emacs deletes the frame you are in. Deleting a frame, like deleting a window, affects only the display. The underlying buffer is still active, and you can move to it by typing C-x b.

If you try to use C-x 5 0 to delete the only frame that is left, Emacs won't do it. To exit Emacs, type C-x C-c or close the frame as you would any other GUI window using the mouse.

To minimize a frame, either minimize it in the usual way or press C-z. 

Keystrokes                      Command name                        Action
                                                                    
C-x 5 o Buffers → Frames        other-frame                         Move to other frame.
C-x 5 0 File → Delete Frame     delete-frame                        Delete current frame.
C-x 5 2 File → New Frame        make-frame                          Create a new frame on the current buffer.
C-x 5 f                         find-file-other-frame               Find file in a new frame.
C-x 5 r                         find-file-read-only-otherframe      Finds a file in a new frame, but it is readonly.
C-x 5 b                         switch-to-buffer-other-frame        Make frame and display other buffer in it.

More About Buffers
Renaming Buffers
    Type M-x rename-buffer 
Read-Only Buffers
    You can make any buffer read-only by pressing C-x C-q.
    You can open a file as read-only in a new window by typing C-x 4 r or in a new frame by typing C-x 5 r. This is one of a number of commands in which 4 means window and 5 means frame.
Getting a List of Buffers
    C-x C-b
Working with the Buffer List
    The buffer list is more than a display. From the buffer list, you can display, delete, and save buffers.
    To move to the buffer list window, type C-x o.

Keystrokes                              Command name            Action
                                                                
C-x b Buffers → Select Named Buffer     switch-to-buffer        Move to the buffer specified.
C-x → Buffers → Next Buffer             next-buffer             Move to the next buffer in the buffer list.
C-x Buffers → Previous Buffer           previous-buffer         Move to the previous buffer in the buffer list.
C-x C-b Buffers → List All Buffers      list-buffers            Display the buffer list.
C-x k                                   kill-buffer             Delete the buffer specified.
(none)                                  kill-some-buffers       Ask about deleting each buffer.
(none)                                  rename-buffer           Change the buffer's name to the name specified.
C-x s                                   save-some-buffers       Ask whether you want to save each modified buffer.


Keystrokes              Action                                                                              Occurs
                                                                                                            
C-n, Space, n, or       Move to the next buffer in the list (i.e., down one line).                          Immediately 
C-p,p, or               Move to the previous buffer in the list (i.e., up one line).                        Immediately 
d                       Mark buffer for deletion.                                                           When you press x
k                       Mark buffer for deletion.                                                           When you press x
s                       Save buffer.                                                                        When you press x
u                       Unmark buffer.                                                                      Immediately 
X                       Execute other one-letter commands on all marked buffers.                            Immediately 
Del                     Unmark the previous buffer in the list; if there is no mark, move up one line.      Immediately 
~                       Mark buffer as unmodified.                                                          Immediately 
%                       Toggle read-only status of buffer.                                                  Immediately 
1                       Display buffer in a full screen.                                                    Immediately 
2                       Display this buffer and the next one in horizontal windows.                         Immediately 
f                       Replace buffer list with this buffer.                                               Immediately 
o                       Replace other window with this buffer.                                              Immediately 
m                       Mark buffers to be displayed in windows.                                            When you press v
v                       Display buffers marked with m; Emacs makes as many windows as needed.               Immediately
q                       Quit buffer list.                                                                   Immediately

More About Windows
Creating Vertical or Side-by-Side Windows
    To split the window vertically into two side-by-side windows, type C-x 3.
    To see the rest of the line, you need to know how to scroll text to the left and right. To push the text currently being displayed to the left (so you can see what's on the right), type C-x <. Left arrows or dollar signs are displayed on the left side of the window to indicate that there is more text to the left. To push the text being displayed to the right (so you can see what's on the left), type C-x >. 

Navigating Windows
    C-x o moves you to the "next" window

Enlarging and Shrinking Windows
    If you want to make the window you're working on taller, type C-x ^.
    To make the current window wider, type C-\*}. 
    To shrink a window vertically, type M-x shrink-window.
    To shrink a window horizontally, type C-x {. 
    When you type C-u preceding any of these commands, the command works in increments of four lines or columns at a time. 

    you can shrink the window to the size of the buffer by typing C-x - (for shrink-window-if-larger-than-buffer). 
    Typing C-x + (for balance-windows) creates windows of equal size again.

Limits on Window Size
This limit is specified by the variables window-min-height (whose default is four lines) and window-minwidth (whose default is ten characters). 

Comparing Files Between Windows
    Go to the beginning of each buffer, then type M-x comparewindows.
    The Unix diff command provides a more comprehensive (although somewhat awkward looking) way to find the differences between two files. 
    Emacs also provides an interface to Ediff, with options on the Compare menu (a submenu of the Tools menu). Ediff is far more comprehensive; see Chapter 12 for details.

Keystrokes                                                      Command name                            Action
                                                                                                        
C-x 2 File → Split Window                                       split-window-vertically                 Divide current window into two windows, one above the other.
C-x 3                                                           split-window-horizontally               Divide current window into two side-by-side windows.
C-x >                                                           scroll-right                            Scroll the window right.
C-x <                                                           scroll-left                             Scroll the window left.
C-x o                                                           other-window                            Move to the other window; if there are several, move to the next window (see "Navigating Windows").
C-x 0                                                           delete-window                           Delete the current window.
C-x 1 File → Unsplit Windows                                    delete-other-windows                    Delete all windows but this one.
(none)                                                          delete-windows-on                       Delete all windows on a given buffer.
C-x ^                                                           enlarge-window                          Make window taller.
(none)                                                          shrink-window                           Make window shorter.
C-х }                                                           enlarge-window- horizontally            Make window wider.
C-x {                                                           shrink-window- horizontally             Make window narrower.
C-x -                                                           shrink-window-if-largerthan-buffer      Make window smaller if buffer is smaller than window.
C-x +                                                           balance-windows                         Make windows the same size.
C-M-v                                                           scroll-other-window                     Scroll other window.
C-x 4 f                                                         find-file-other-window                  Find a file in the other window.
C-x 4 b                                                         switch-to-buffer-otherwindow            Select a buffer in the other window.
(none) Tools → Compare (Ediff) → This Window and Next Window    compare-windows                         Compare this window with the next window and show the first difference.

Holding Your Place with Bookmarks

Setting Bookmarks
C-x r m

Moving to a Bookmark
C-x r b

Renaming and Deleting Bookmarks
M-x bookmark-rename
M-x bookmark-delete

Command             Action
                    
Enter ,f, or j      Go to the bookmark on the current line.
C-o or o            Open the bookmark on the current line in another window; o moves the cursor to that window; C-o keeps the cursor in the current window.
d. C-d , or k       Flag bookmark for deletion.                           
r                   Rename bookmark.                                      
s                   Save all bookmarks listed.                            
m                   Mark bookmarks to be displayed in multiple windows.   
v                   Display marked bookmarks or the one the cursor is on if none are marked.
t                   Toggle display of paths to files associated with bookmarks.
w                   In the minibuffer, display location of file associated with bookmark.
x                   Delete bookmarks flagged for deletion.                
u                   Remove mark from bookmark.                            
Del                 Remove mark from bookmark on previous line or move to the previous line (if there is no mark).
q                   Exit bookmark list.
Space or n          Move down a line.
p                   Move up a line.
l                   Load a bookmark file (other than the default).
A                   Display all annotations.
a                   Display annotation for current bookmark.
e                   Edit (or create) annotation for the current bookmark.

Annotation Bookmarks
Open the bookmark list using C-x r l, then move to the line of the bookmark you want to annotate. 
    Type e, the command to edit an annotation.
    Press C-c C-c to save and exit the annotations buffer.

If you set a bookmark, Emacs saves the bookmarks file automatically (and in fact without asking). If you set an annotation but do not add or move a bookmark during the session, you must save the bookmarks file manually by typing M-x bookmark-save.

A Few More Bookmark Commands

Keystrokes                                          Command name                    Action                                                      
                                                                                    
C-x r m Edit → Bookmarks → Set Bookmark             bookmark-set                    Set a bookmark at the current cursor position.
C-x r b Edit → Bookmarks → Jump to Bookmark         bookmark-jump                   Jump to a bookmark.
(none) Edit → Bookmarks → Rename Bookmark           bookmark-rename                 Rename a bookmark.
(none) Edit → Bookmarks → Delete Bookmark           bookmark-delete                 Delete a bookmark.
(none) Edit → Bookmarks → Save Bookmarks            bookmark-save                   Save all bookmarks in default file.
C-x r l Edit → Bookmarks → Edit Bookmark List       bookmark-menu-list              Move to *Bookmark List* buffer.
(none) Edit → Bookmarks → Insert Contents           bookmark-insert                 Insert full text of file associated with a given bookmark.
(none ) Edit → Bookmarks → Save Bookmarks As        bookmark-write                  Save all bookmarks in a specified file.
(none) Edit → Bookmarks → Load a Bookmark File      bookmark-load                   Load bookmarks from specified file.
(none) Edit → Bookmarks → Insert Location           bookmark-insert-location        Insert the path to a given bookmark at the cursor position.
