Link
---
https://leetcode.com/problems/subdomain-visit-count/description/

Mine Code
```
class Solution {
public:
    vector<string> subdomainVisits(vector<string>& cpdomains) {
        
        map<string,int> visit_count;
        for(int i=0;i<cpdomains.size();i++)
        {
            int find_index = cpdomains[i].find(' ');
            int count = stoi(cpdomains[i].substr(0,find_index));
            string domain = cpdomains[i].substr(find_index+1,cpdomains[i].size()-find_index-1);
            
            //one domain may appear many times
            visit_count[domain] += count;
            while(1)
            {
                find_index = domain.find_first_of('.');
                if(find_index==-1)
                {
                    break;
                }
                domain = domain.substr(find_index+1,domain.size()-find_index-1);
                visit_count[domain] += count;

            }
        }
        
        vector<string> result;
        for(map<string,int>::iterator iter = visit_count.begin();iter!=visit_count.end();iter++)
        {
            result.push_back(to_string(iter->second)+" "+iter->first);
        }
        
        return result;
    }
};
```
