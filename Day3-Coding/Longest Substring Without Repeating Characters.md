class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        di={}
        #mini=0
        maxlen=0
        for i in range(len(s)):
            if s[i] in di.keys():
                maxlen=max(maxlen,len(di))
                n=s[:di[s[i]]]
                n.replace(s[i],"")
                for j in range(len(n)):
                    if n[j] in di.keys():
                        if di[n[j]] < di[s[i]]:
                            del di[n[j]]
                di[s[i]]=i
            else:
                di[s[i]]=i
            if i==len(s)-1:
                di[s[i]]=i
                maxlen=max(maxlen,len(di))
                return maxlen
        return maxlen
                
            
            
        
