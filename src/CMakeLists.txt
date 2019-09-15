# The MIT License (MIT)
#
# Copyright (c) 2019 Mateusz Pusz
#
# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:
#
# The above copyright notice and this permission notice shall be included in all
# copies or substantial portions of the Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
# SOFTWARE.

include(metabench)

metabench_add_dataset(data.conditional.std
    conditional_std.cpp.erb "[10, 500, 1000, 2000, 5000, 10000, 15000, 20000, 30000]"
    NAME "std::conditional"
)
metabench_add_dataset(data.conditional.alias
    conditional_alias.cpp.erb "[10, 500, 1000, 2000, 5000, 10000, 15000, 20000, 30000]"
    NAME "conditional alias"
)
metabench_add_dataset(data.conditional.alias_no_helper
    conditional_alias_no_helper.cpp.erb "[10, 500, 1000, 2000, 5000, 10000, 15000, 20000, 30000]"
    NAME "conditional alias no helper"
)
metabench_add_chart(chart.conditional ALL
    TITLE "conditional"
    SUBTITLE "(lower is better)"
    DATASETS
        data.conditional.std
        data.conditional.alias
        data.conditional.alias_no_helper
)

metabench_add_dataset(data.is_same.std
    is_same_std.cpp.erb "[10, 500, 1000, 2000, 5000, 10000, 15000, 20000, 30000]"
    NAME "std::is_same_v"
)
metabench_add_dataset(data.is_same.std_no_helper
    is_same_std_no_helper.cpp.erb "[10, 500, 1000, 2000, 5000, 10000, 15000, 20000, 30000]"
    NAME "std::is_same::value"
)
metabench_add_dataset(data.is_same.variable
    is_same_variable.cpp.erb "[10, 500, 1000, 2000, 5000, 10000, 15000, 20000, 30000]"
    NAME "is_same variable"
)
metabench_add_chart(chart.is_same ALL
    TITLE "is_same"
    SUBTITLE "(lower is better)"
    DATASETS
        data.is_same.std
        data.is_same.std_no_helper
        data.is_same.variable
)
