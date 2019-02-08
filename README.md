# FindDiff

## This Application finds the difference between a source and a destination .xlsx file.
import pandas as pd

def load_files():
    ps = pd.read_excel('./Source.xlsx')
    pa = pd.read_excel('./Second.xlsx')
    column_dic = {}
    column_list =[]
    i=1
    for col in ps.columns:
        column_dic[i] = col
        i+=1
    print (column_dic)
    while (True):
        temp= input("Please enter column number to be "
                                     "compared in separate lines "
                "and type 'done' to finish"
                ": ")
        if temp == 'done':
            break
        elif not(temp.isdigit()):
            print("Please enter valid value")
            continue
        elif int(temp) >= i:
            print("Please enter valid value")
            continue
        else:
            column_list .append(column_dic[int(temp)])


load_files()
