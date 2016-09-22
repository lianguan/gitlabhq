FROM gitlab/gitlab-ce:8.11.7-ce.0
MAINTAINER Shiliang Guan <guanshiliang@gmail.com>

RUN echo "" \
    && echo "# git clone https://github.com/phecho/gitlabhq.git" \
    && git clone https://github.com/phecho/gitlabhq.git \
    && echo "# Generating translation patch" \
    && cd gitlabhq \
    && git diff origin/8-11-stable..origin/8-11-stable-zh > ../zh_CN.diff \
    && echo "# Patching" \
    && patch -d /opt/gitlab/embedded/service/gitlab-rails -p1 < ../zh_CN.diff \
    && echo "# Cleaning" \
    && cd .. \
    && rm -rf gitlabhq \
    && rm *.diff
