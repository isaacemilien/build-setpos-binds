import sys

if len(sys.argv) < 2:
    sys.exit(1)

user_input = sys.argv[1:]

output = f'''
// Aliases 
alias "prevPos" "pos{len(user_input)}" 
alias "nextPos" "pos2"

alias "pos1" "{user_input[0]}; alias prevPos pos{len(user_input)}; alias nextPos pos2;"'''

for i in range(len(user_input) - 1):
    if i == 0: continue 
    output += f'\nalias "pos{i + 1}" "{user_input[i]}; alias prevPos pos{i}; alias nextPos pos{i + 2};"'

output += f'''
alias "pos{len(user_input)}" "{user_input[len(user_input) - 1]}; alias prevPos pos{len(user_input) - 1}; alias nextPos pos1;"

// Binds 
bind "mouse4" "prevPos" 
bind "mouse5" "nextPos"'''

print(output)
