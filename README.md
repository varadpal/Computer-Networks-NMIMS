# Computer-Networks-NMIMS
This repository contains all the documents containing necessary Lab Experiments for Computer Networks for NMIMS.

## Experiment 5 Code
    # Function To Check If The IP Address Is Valid
    def validity(ip):
        y = ip.split( "." )
        result = []
        err = 0
        for i in y:
            bucket = int(i)
            result.append(bucket)
            if bucket > 255 or bucket < 0:
                err += 1
        
    
        if len(result) != 4:
            print("Invalid IP Address")
        
        elif err > 0: 
            print("Invalid IP Address")
        else: 
            print("Valid  IP Address...")
            return result
    
    
    # Function To Classify The IP Address in Class 'A', 'B', 'C', 'D'
    def classify(add):
        i = add[0] 
        if i >= 1 and i <= 126: 
            print("IP Address is of Class A.")
        
        elif i >= 127 and i <= 191: 
            print("IP Address is of Class B.")
                
        elif i >= 192 and i <= 223: 
            print("IP Address is of Class C.")
                
        elif i >= 224 and i <= 239: 
            print("IP Address is of Class D.")
    
    
    # Function To Convert The Decimal IP To Dotted Decimal Notation (Binary) 
    def ip_to_binary(add):
        binary = []
        for i in add:
            binary.append(bin(i)[2:])
        return binary
    
    
    # Function To Convert IP Dotted Decimal Notation (Binary) To Decimal
    def binary_to_decimal(add):
        decimal = []
        for i in add: 
            decimal.append(int(i,2))
    
        return decimal
    
    
    # Main Program
    x = input("Enter IP Address: ")
    
    ip = validity(x)
    if ip != None:
        print()
        classify(ip)
    
        bin = ip_to_binary(ip)
        print("Binary Ip Address: ", end="")
        for i in bin:
            print(i, end=" ")
    
        print()
        dec = binary_to_decimal(bin)
        print("Decimal Ip Address: ", end="")
        for i in dec:
            print(f"{i}", end=".")
        print()
