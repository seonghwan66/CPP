# kimseonghwan

def ancestor(x, y):
    if x == y: # x와 y가 같은 경우
        return True
    elif x == None: # x가 None인 경우
        return False
    else: # x와 y가 다른 경우
        return ancestor(parent(x), y)
